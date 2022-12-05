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

### Original

- `src_clean`: https://cmu.box.com/shared/static/z6f1iz3nic2d31zxnix3bn4ge7lz69p1
- `src_noisy`: https://cmu.box.com/shared/static/cds26b2grgekszptc17a1ckljuocqyzq

## Train Partitions (1/3)


### Transmitted Audio (Industrial Denoising OFF
- Google Meet To Cloud (`src_gm_cloud_relay_auto`):<br>https://cmu.box.com/shared/static/yii2dlegeh2c6mq8vxkqs3wwbhpc0qfl
- Google Meet To Phone (`src_gm_phone_relay_auto`):<br>https://cmu.box.com/shared/static/8xvo964542i0binzfrrcq6nrbser0cc5
- Zoom To Cloud (`src_zm_cloud_relay_auto`):<br>https://cmu.box.com/shared/static/zk0su4veohr7t4lxesxx117ofzfypzqp
- Zoom To Phone (`src_zm_phone_relay_auto`):<br>https://cmu.box.com/shared/static/dve4yqo2cdfnn8lpp6mo8vddkxac3x2z

### Transmitted Audio (Industrial Denoising ON)
- Google Meet To Cloud (`src_gm_cloud_relay_auto`):<br>https://cmu.box.com/shared/static/fjkhw6sif94own77pua3x1dm264bpj8n
- Google Meet To Phone (`src_gm_phone_relay_auto`):<br>https://cmu.box.com/shared/static/ibel9iy81ig13pml34b1zasnki470lmh
- Zoom To Cloud (`src_zm_cloud_relay_auto`):<br>https://cmu.box.com/shared/static/ddxaemvjzli8oih3zn7i569ypov1fqs3
- Zoom To Phone (`src_zm_phone_relay_auto`):<br>https://cmu.box.com/shared/static/65seuub7gwbhlphkdphk8b44sugojqa8

### Original

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

<!--



- `src_zm_cloud_relay_low`: https://cmu.box.com/shared/static/t2dkw2ocb5wx08nh86jb861l1uhqyfds
- `src_zm_cloud_relay_auto`: https://cmu.box.com/shared/static/gl4rh7dk535wl2l5zvf1ptom1n87iaql


- `src_zm_phone_relay_low`: https://cmu.box.com/shared/static/yavlvg7touvxjok7sfn58neud6a3iuj5
- `src_zm_phone_relay_auto`: https://cmu.box.com/shared/static/qbngbdrpojd1v0zw0fnpp72j7styrqae


- `src_gm_cloud_relay_low`: https://cmu.box.com/shared/static/k0l49zdfefgyn0h7mwcnnvas5f8n7kks
- `src_gm_cloud_relay_auto`: https://cmu.box.com/shared/static/oqucql868ce17kk7lbei48son1holvxh


- `src_gm_phone_relay_low`: https://cmu.box.com/shared/static/jd9jg24ik1e95gt17hz16cwuhghdqnsi
- `src_gm_phone_relay_auto`: https://cmu.box.com/shared/static/ozmxm2syw8mthngs80r0tul3vm7htefk

### Original

- `src_clean`: https://cmu.box.com/shared/static/f3kyi0f2ptoe4klfayao34l82ahrq6sh
- `src_noisy`: https://cmu.box.com/shared/static/w14n5z61shpkbtwnx1ej7zl1n5ei39n8
-->
