# VoIP-DNS-Challenge

## Test Partitions

- `src` = Source Audio
- `nrm` = Normalized Audio
- `zm`  = Zoom
- `gm`  = Google Meets
- `cloud` = Audio Relayed To Cloud.
- `phone` = Audio Relayed To Phone.
- `low` = Low Denoising Setting
- `auto` = Auto Denoising Settting

### Transmitted Audio (Industrial Denoising OFF
- Google Meet To Cloud (`src_gm_cloud_relay_auto`):<br>https://cmu.box.com/shared/static/3fiv8we5y6ofoutxa1agq2vc2onrc0gd
- Google Meet To Phone (`src_gm_phone_relay_auto`):<br>https://cmu.box.com/shared/static/h4qtwwzyzsbccpzofd7w9dye00olvv16
- Zoom To Cloud (`src_zm_cloud_relay_auto`):<br>https://cmu.box.com/shared/static/i3n42m5vxmtphz3ko4oent9y9cbylqck
- Zoom To Phone (`src_zm_phone_relay_auto`):<br>https://cmu.box.com/shared/static/w45x9viyn6ugif32qa7vjvzi99onjhe1

### Transmitted Audio (Industrial Denoising ON)
- Google Meet To Cloud (`src_gm_cloud_relay_auto`):<br>https://cmu.box.com/shared/static/do9pb9sscnq5js6omvmu0wymtysxifwz
- Google Meet To Phone (`src_gm_phone_relay_auto`):<br>https://cmu.box.com/shared/static/72f495okfp3r4y0tdpkx9xz0510uu9o5
- Zoom To Cloud (`src_zm_cloud_relay_auto`):<br>https://cmu.box.com/shared/static/f4vjganno2i05dlpu517rjfuwy4cr7do
- Zoom To Phone (`src_zm_phone_relay_auto`):<br>https://cmu.box.com/shared/static/m05ovewmx0hdcpx5uzsorn8f8ec74br2

### Original Audio

- `src_clean`: https://cmu.box.com/shared/static/z6f1iz3nic2d31zxnix3bn4ge7lz69p1
- `src_noisy`: https://cmu.box.com/shared/static/cds26b2grgekszptc17a1ckljuocqyzq

## Train Partitions

All Sets:
https://drive.google.com/drive/folders/1hIVTl26mu7zAvMFYY6HTGYSdhNYy41Oz?usp=sharing

### Original Audio

- `src_clean`: https://cmu.box.com/shared/static/2c8wabvnh10j4izz4t5jv4ewt9xmotxd
- `src_noisy`: https://cmu.box.com/shared/static/s/74eqhujlzubq8q4qp0ju307csgii9iky

## (Optional) Gain Normalization

```
import numpy as np

def gain_normalize(waveform):

    amplitude = np.iinfo(np.int16).max
    waveform  = np.int16(0.8 * amplitude * waveform / np.max(np.abs(waveform)))

    return waveform
```

## Industry Source Baseline Evaluation

```
src_gm_cloud_relay_low                          src_gm_cloud_relay_auto

                 relay      fsnet      demuc                     relay      fsnet      demuc
composite_0   1.624786   2.290229   3.081065    composite_0   2.119337   2.107558   2.744660
composite_1   2.113809   2.682689   2.616326    composite_1   2.455719   2.508279   2.458059
composite_2   1.599932   2.359505   2.676537    composite_2   2.185469   2.193002   2.500239
csii_0        0.813946   0.856926   0.858317    csii_0        0.796703   0.796744   0.798324
csii_1        0.627126   0.717041   0.725775    csii_1        0.674261   0.675282   0.678533
csii_2        0.306212   0.474009   0.490636    csii_2        0.451206   0.460325   0.465031
fwSNRseg      9.821719  11.698387  12.085520    fwSNRseg     11.148064  11.156726  11.287034
llr           1.653221   1.601247   1.031627    llr           1.628586   1.633495   1.272214
ncm           0.789861   0.878290   0.882312    ncm           0.827219   0.826965   0.830074
pesq          1.640381   2.436527   2.274188    pesq          2.256759   2.282958   2.265513
SNRseg       -0.809785   0.947340   0.975914    SNRseg       -1.326726  -0.705255  -1.277742
stoi          0.893047   0.929526   0.933718    stoi          0.923730   0.923635   0.924552
wss          36.182449  25.093309  23.745548    wss          24.775441  24.649134  25.479798

src_gm_phone_relay_low                          src_gm_phone_relay_auto

                 relay      fsnet      demuc                     relay      fsnet      demuc
composite_0   1.643514   1.120086   1.780431    composite_0   2.162253   1.300821   2.099590
composite_1   1.970019   1.800457   1.925734    composite_1   2.338397   2.099986   2.220504
composite_2   1.528438   1.096679   1.518393    composite_2   2.050029   1.353364   1.892613
csii_0        0.461290   0.409957   0.457264    csii_0        0.668191   0.634685   0.664981
csii_1        0.311832   0.288361   0.314371    csii_1        0.549327   0.500497   0.535272
csii_2        0.092208   0.101617   0.118038    csii_2        0.337895   0.272278   0.327579
fwSNRseg      4.264036   4.066358   4.905078    fwSNRseg      7.983082   6.859297   7.883913
llr           1.505411   1.658952   1.394086    llr           1.440653   1.661855   1.412963
ncm           0.585810   0.474626   0.568569    ncm           0.715571   0.625459   0.692941
pesq          1.548908   1.302429   1.371009    pesq          1.977029   1.513223   1.724669
SNRseg       -0.610556  -0.800124  -0.437866    SNRseg       -0.331891   0.142401  -0.340463
stoi          0.748711   0.675699   0.710409    stoi          0.884854   0.822833   0.865313
wss          52.270603  57.956579  48.003199    wss          31.387709  38.043698  30.919717

src_zm_cloud_relay_low                          src_zm_cloud_relay_auto

                 relay      fsnet      demuc                     relay      fsnet      demuc
composite_0   1.576560   2.049113   2.939564    composite_0   2.031721   1.903576   2.591427
composite_1   1.960566   2.436467   2.505097    composite_1   2.305990   2.289655   2.364531
composite_2   1.469259   2.073959   2.504300    composite_2   1.958048   1.928563   2.278276
csii_0        0.737295   0.781632   0.786108    csii_0        0.786678   0.789748   0.790951
csii_1        0.576722   0.661505   0.676134    csii_1        0.653957   0.659650   0.665634
csii_2        0.265271   0.414289   0.434970    csii_2        0.377564   0.400288   0.404253
fwSNRseg      9.453901  11.363387  11.977132    fwSNRseg     10.532511  10.558066  10.729410
llr           1.587811   1.589108   1.026003    llr           1.531042   1.609715   1.254754
ncm           0.789886   0.886119   0.890747    ncm           0.883708   0.889505   0.894490
pesq          1.455911   2.141213   2.091157    pesq          1.920564   1.983857   1.997478
SNRseg       -0.929837   0.036253   1.113084    SNRseg       -0.455298  -1.348469  -0.222629
stoi          0.859611   0.900330   0.906172    stoi          0.909878   0.911533   0.913781
wss          44.397111  31.902437  28.371543    wss          31.050818  29.667892  30.034001

src_zm_phone_relay_low                          src_zm_phone_relay_auto

                 relay      fsnet      demuc                     relay      fsnet      demuc
composite_0   1.246709   1.107946   1.721702    composite_0   1.631155   1.163136   1.673486
composite_1   1.952766   1.826324   1.955394    composite_1   2.114226   1.828537   2.019329
composite_2   1.289245   1.094889   1.498630    composite_2   1.609949   1.125019   1.539145
csii_0        0.631916   0.548921   0.628053    csii_0        0.497127   0.435423   0.490983
csii_1        0.474023   0.405017   0.460387    csii_1        0.386788   0.324556   0.373641
csii_2        0.189784   0.168967   0.217507    csii_2        0.167616   0.108569   0.159157
fwSNRseg      4.805176   4.445922   5.555838    fwSNRseg      5.635491   4.641343   5.723839
llr           1.711517   1.707672   1.439694    llr           1.520138   1.623604   1.489878
ncm           0.666949   0.523838   0.652001    ncm           0.682211   0.491804   0.649112
pesq          1.548824   1.301811   1.381417    pesq          1.701747   1.256231   1.513012
SNRseg       -0.795692  -0.942946  -0.348657    SNRseg       -0.405368  -0.845370  -0.373910
stoi          0.797549   0.714282   0.765057    stoi          0.810592   0.693265   0.783409
wss          53.063360  52.933685  45.279712    wss          43.953029  50.383238  44.904837
```
