# Migration Manifest — TextyMcSpeechy

- source: Google Drive
- source_folder: `Codigos_Antes_Exportados/TextyMcSpeechy`
- project_family: `TextyMcSpeechy`
- github_repository: `wpv10barza/textymcspeechy`
- github_branch: `main`
- github_commit: `ed700e51387e9334822a00104171904e6435fae0`
- files_migrated: 41
- verification_status: `VERIFIED`
- verified_at: `2026-09-29`

## Exclusiones deliberadas

No se versionan los directorios de datos/modelos generados: `tts_dojo/DATASETS`, `tts_dojo/PRETRAINED_CHECKPOINTS`, `DOJO_CONTENTS/training_folder`, `voice_checkpoints`, `tts_voices`, `archived_*`, `target_voice_dataset`, `starting_checkpoint_override`, ni `dataset_recorder/wav`. Tampoco se migra `.git`.

### Dataset VCTK

El script de Drive registra para `VCTK-Corpus-0.92.zip` un tamaño esperado de **11,747,302,977 bytes** y descarga desde el repositorio de datos de la University of Edinburgh. El dataset no se copia a GitHub; se reproduce con `VCTK_dataset_tools/download_vctk_dataset.sh`. No se calcula SHA-256 del corpus completo porque no se materializa dentro de esta migración.

## Normalización

Los scripts `.sh` del Drive usan CRLF. La copia canónica se normaliza a LF para ejecución Unix. Los hashes de origen y canónicos se registran a continuación.

## SHA-256

| Archivo | SHA-256 origen Drive | SHA-256 canónico |
|---|---|---|
| `.gitignore` | `56e49e963205beaf562732c2731769c3f4d896d07ca8c81d1ace342143254ff3` | `040b081c2f5a830855d065737128f61194403339440e7169220bcefd05232545` |
| `Dockerfile` | `5bd7a962fbce877c26fec13a1ceeec591eded65b230f24a87536b1daaa505867` | `5bd7a962fbce877c26fec13a1ceeec591eded65b230f24a87536b1daaa505867` |
| `LICENSE` | `c456653494f8741cc621269cfd5ee03bff13ac65b38985b9b0f144066baf7661` | `07c8c8ca0cca3333cebf804f282c7fd0d7db0cf50335542c70371ecd21ab2e04` |
| `README.md` | `ddcaae3a56ee91e802957e8d8459650c12a7e7ad16cc8f075c53ea4a52bd5bff` | `ddcaae3a56ee91e802957e8d8459650c12a7e7ad16cc8f075c53ea4a52bd5bff` |
| `VCTK_dataset_tools/batch_resample_and_convert.sh` | `99c2142a74136164c65baca34951e0b009cb31a7d9a7a2e2c983b48d767cdc0f` | `4f94612e37b683d7c5a99406e8cec13c607fe28dc8e2928bb3b1acaee1c3ee49` |
| `VCTK_dataset_tools/download_vctk_dataset.sh` | `5b10b314ec833a88a909e334a49484fa625e76ad9e54b899189ce67295e384b9` | `c991b4506b2dbe630301eb72f7eee68e597c532e1072740ba28772e2d94894a0` |
| `VCTK_dataset_tools/single_voice_from_VCTK_dataset.sh` | `653ac56b33f1a8ca4e549910c0164115895011b8b427598df8bb25d800f57522` | `cca754f5659d097dbf7960b17376a2fb8a7d09e128fc5322a2d27925580dc477` |
| `VCTK_dataset_tools/using_vctk_dataset.md` | `57bcd988ad3674905a098ef87dc9f0988668c9f7866bd8942310b90a5d08de60` | `57bcd988ad3674905a098ef87dc9f7866bd8942310b90a5d08de60` |
| `batch_audio_tools/batch_change_sampling_rate.sh` | `f772af1947bfac757ed0c9600f51f4b73444b23cd4c619a5d817ed4a00c3b4e2` | `bf911c74fdaaf93cfe8c7de87959ec14a7091a8c65e3e65d9559d8d8efa0842a` |
| `batch_audio_tools/checkrate.sh` | `fd3ee553f7ddc2e82c81f7937847568de1123de40400aac823aa7f1df6947498` | `1d9ebc481c82f783c4560101cd4bb58532b4711983372de1cfbb832da0d40dba` |
| `batch_audio_tools/sift_soundfiles.sh` | `039d04398d57d76ce8aaf58176d41a61c8d44e9d4becc00356c8b4b6be09bbe1` | `1650b82c12ed5440adf372a948e916c2a2bb14f7b4269380d089c2449eefb5a4` |
| `dataset_recorder/dataset_recorder.sh` | `4716db6d10ccbd4e3d366c35ade99f8a1f851023537197c7d5c72cc085daf3b3` | `e46f476ec0af78f3efb2d49f0c4734dd9aec0948f61b553dbb63278730a595d7` |
| `dataset_recorder/dataset_recorder_README.md` | `22ac66284041acf351c84ef67b4830afdc7e932ac36bd575e09e728bdb168817` | `22ac66284041acf351c84ef67b4830afdc7e932ac36bd575e09e728bdb168817` |
| `dataset_recorder/remove_roomtone.sh` | `9ffb7cd1427a3c935197e1b557958be3d1623d6a2baa785f8831c7ea1f38f683` | `3e02844e91bb80d7e52b84939574764469bccf3a90dbeb816516af5b94763e7b` |
| `docker-compose.yml` | `609adccae50c1dd16266fa21796ceb2ab29432b5d782c8f78dc9710fec53dd5d` | `609adccae50c1dd16266fa21796ceb2ab29432b5d782c8f78dc9710fec53dd5d` |
| `local_container_run.sh` | `005e45c81377ecf759840826c917d032679c4bb9acc4ebce0fcd4b6414a82db5` | `36c1461d9db584266c734883f539fd0dc6f795b5f21dd59465ef2e4f602b0ca7` |
| `prebuilt_container_run.sh` | `d28c69f85690b07a5b28f7a022248c98a1bf677f5b95a1cfe31249fe129fe445` | `509db600087a8d6a3f711b971dbd17cc9c007aa73c42108e704072aca2a8506c` |
| `quick_start_guide.md` | `c2f9056576f8ff61ed012a1ca0a2a51cae4a7cd480663cd998ece1d8ff1e0408` | `c2f9056576f8ff61ed012a1ca0a2a51cae4a7cd480663cd998ece1d8ff1e0408` |
| `run_container.sh` | `ea944cdece38b041327877c2c6e42c51df8228f8cb49a0a98f4c70ab8fb621e5` | `d013145706492be4d94ec0f74e18772f0d63a72940b7d7f6dd8be0b922cd5cfe` |
| `setup.sh` | `f1c846f2fddaaddfbda23de9a72572bbf4437e90163fec23274db520e5df6566` | `6ebb5f5c59fa93aad940d5d5c929d20e154c68f06b68667cdb1b7f570cae7ceb` |
| `stop_container.sh` | `568b12d966711f28a05a5f62a8cfe04664f0094d7bae862d7ae471db08166e2c` | `ec4a0cccf7798f93ce151eb075b0de736b62bede5023ceab0872853bfb0e5e47` |
| `tts_dojo/DOJO_CONTENTS/run_training.sh` | `2b44c54962619ee3cfa48fc1b2cd032208add95c7d8d3d266f3a5b0e7f03e986` | `77f9efa29100f4159760d67d242c9bfbe084ce36167673db18cd08a8ab1f7ed3` |
| `tts_dojo/DOJO_CONTENTS/scripts/SETTINGS.txt` | `7a39f12905cf0f5550f19093ea6fde17462617baa9e1f6469667d9f370a83378` | `7a39f12905cf0f5550f19093ea6fde17462617baa9e1f6469667d9f370a83378` |
| `tts_dojo/DOJO_CONTENTS/scripts/link_dataset.sh` | `385615f99cdda8cab6cadfa4c491685adfd0c34459922630bafcaed8044b573f` | `a3521637691dcafe4df0d254af6cfc6d31c948813a4e023594966e15c35d29f3` |
| `tts_dojo/DOJO_CONTENTS/scripts/preprocess_dataset.sh` | `a5068b719afe74e7b51cba315b9d9f7a02c7c1531161c75fdd61135799a08032` | `1535f6f397f0d8afb332c461cd33feeeb02b7237915c2de90dd878d50f61d6cd` |
| `tts_dojo/DOJO_CONTENTS/scripts/restore_tmux_layout.sh` | `1eaf891e2bc6ec5460a878f30bdc3a2970eabfac4fc162b443215d25dbbf1173` | `126c754b78422b0ac3fa7762fc9dc8d98c974f3d0e28a09df5edfe7a93fd11e1` |
| `tts_dojo/DOJO_CONTENTS/scripts/save_tmux_layout.sh` | `c6cf04775d1bcb75aca12c404c6667b40de2c3f72be8cd341a8964176c5e3212` | `7d0ec9b150068413bebabb12719f3c0f9ee06da7f96d10da84870119e9e3172d` |
| `tts_dojo/DOJO_CONTENTS/scripts/train.sh` | `c2e985a2bc5fef0d01093a5ec1667cff2dea9aac55641a946eb3cb4b7b7a19da` | `90a7684142faad2fbe7ee6cf175412406a60b984787c6e6cdf60f23be5f6ce49` |
| `tts_dojo/DOJO_CONTENTS/scripts/tts.sh` | `9b3693b194b407b68fa327e6debd2f49f7c37fd608ca92db69b534cd145da045` | `535fd3d4606aae2c07dee6bfe117a1145ba14ad8d41c5ed50df887234f215730` |
| `tts_dojo/DOJO_CONTENTS/scripts/utils/_control_console.sh` | `3014842cb1753c6d4bd3c11fa1a395dc8e118a82a857d9025e870216ae218949` | `b7d53dc0f80f23b73f75a40a0830e2cd11910254f2ed72e36e30bc2e29ab0820` |
| `tts_dojo/DOJO_CONTENTS/scripts/utils/_tmux_piper_export.sh` | `e0ca6490e934e556c146b77d30274a763e43332ac29e99fcbaa6cd120803a939` | `fca75137b6abaa1fd42d23f693055b20a0aa188f4b3626c4e1f63f11267c7537` |
| `tts_dojo/DOJO_CONTENTS/scripts/utils/checkpoint_grabber.sh` | `b330634aaf65c946daad179b60c702f45ff10dcc00198abfc27f01b400d9b0b2` | `7741b7714898e1c47ec00adaae81f0999011d0af2296ba1425e8b0a8f1c91e13` |
| `tts_dojo/DOJO_CONTENTS/scripts/utils/piper_training.sh` | `a25482b53bb9c6ccd3b0e2dd782c7a4b75ad9a58a81ed15e15a4c70326343c54` | `1469d5c3aeaa0b88126cddfc15f5a2bce8b77ad83452f6b5563f5c0e0f49a98b` |
| `tts_dojo/DOJO_CONTENTS/scripts/utils/run_tensorboard_server.sh` | `595d6070b0057b9e52ea6886110217b1d6d0bac4a4f2c7c9542b99e4a90768f9` | `b59f42de77b290e379a4d978b03d48230c138557189d9eeb874dbcea66eb0ac0` |
| `tts_dojo/DOJO_CONTENTS/scripts/voice_tester.sh` | `3b34d3f5ae7730bfc3bd39db46a89274ab62866feb4fa44af9121464dacec696` | `585dc9c4ba7fb46e0aaf60150ed7fb780e2661f07d10e83747a0556b6ed19d68` |
| `tts_dojo/ESPEAK_RULES/README_custom_pronunciation.md` | `41f18aa16f21636f1161ff30efdf5e002060b33e2108564d3e26c4e6474ea0b6` | `41f18aa16f21636f1161ff30efdf5e002060b33e2108564d3e26c4e6474ea0b6` |
| `tts_dojo/ESPEAK_RULES/apply_custom_rules.sh` | `a1a3bf6be273c5d5d6a3f5cd50787ecffa9e7f293a74f35620f68697557a3252` | `e1fe1a414ffc7ef868faf453d348f2ebcf0b9659a3aa59d051828e840268c8f7` |
| `tts_dojo/ESPEAK_RULES/automated_espeak_rules.sh` | `c663f7db343986630986b493cee1121759cab73f479565e5750f9e2db4fc32e0` | `eee7e043965e1e8fc4c479e91069e90ae40798601b6db0f38d68f93f89f3ebe4` |
| `tts_dojo/ESPEAK_RULES/container_apply_custom_rules.sh` | `03ba0846186754c6888e4d508a78400619620da4acdcd47ac0427699f8074855` | `7f453b71bfbe77170fa188529c9a1c892cffce670e98ea1870780e83701e536f` |
| `tts_dojo/TTS_dojo_guide.md` | `77f63f95af7241d08306e8f57dac783cc13bb6722888efa05d5b77816d116104` | `77f63f95af7241d08306e8f57dac783cc13bb6722888efa05d5b77816d116104` |
| `tts_dojo/newdojo.sh` | `ea2682810cafc85049d9a00006f734100b43c558fa7053c52b5489e9924fca8d` | `5d72635cb17b0cf9296f8f469022a15d5e91283bfae3067365b76d2bf8a1455b` |


## Verificación final

- import_head: `22bd900a533536a40fc89ad64835531d2c90e9fd`
- merge_commit: `ed700e51387e9334822a00104171904e6435fae0`
- pull_request: `#1`
- PR CI: `success` (run `36605216457`)
- post-merge CI: `success` (run `36605287863`)
- final_tree_checked: `TRUE`
- large_file_git_blob_train: `66ad9740afaf93c30a5570953e2a35a220b9e474`
- large_file_git_blob_checkpoint_grabber: `e337c7418f9481afd18feadfeb27688b89757a28`
- deletion_allowed: `FALSE`
- drive_status: `CONSERVADO`
- deletion_reason: El origen contiene datasets, audio, checkpoints y modelos deliberadamente excluidos del repositorio canónico; por tanto la carpeta completa de Drive no es un respaldo redundante eliminable.
