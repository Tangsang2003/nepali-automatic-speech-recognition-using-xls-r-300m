# nepali-automatic-speech-recognition-using-xls-r-300m
Developing a Nepali automatic speech recognition system with the XLS-R 300M model.

## Before September 16, 2024
- Training was performed on `CommonVoice 17.0` dataset.
- [This](./scripts/FineTuning-XLSR-300-m-on-Common-Voice-17-0-ne-NP.ipynb) notebook was used. Use this notebook for images for reports.
- [This](./scripts/Inference_Test.ipynb) was used for inferences. I mistakenly used `common_voice_test` as the validation set. So, use `common_voice_dev` as the test set.

## After September 16, 2024
- New tokenizer was made from new vocabulary obtained from OpenSLR dataset.
- Training was continued using the previously trained model (`the model mentioned above`). Since, new vocabulary contained additional `Nepali alphabets,` it threw some error about size mismatch or something. I simply used `ignore_size_mismatch=True`. I don't know if this is the correct approach. 
- A function to map Nepali numerals to words was implemented. Though, I am not sure, if this is the way to go. I don't know if this conversion will further confuse the model or will help it in generalization, because upon closer inspection of the dataset, I have found many inconsistencies in pronounciation of numerals. So, this conversion is just an educated wish. IFYKYK.
- [This](./scripts/XLS_R_300_OpenSLR.ipynb) notebook contains all the training setup and different data preprocessing steps. It has the mapping function as well.
- [This](./scripts/Inference_Test_Open_SLR.ipynb) notebook is the modified version of previous inference notebook. I have tried to compare our model with our previous `Common Voice` model and a model that I found on `HuggingFace`. The comparision was done on `CommonVoice` test set. 
- My training session timed out after `1.3` epochs. So, need to continue later. And obviously the results are very poor till now.
- [Here](/Images/Training%20on%20OpenSLR/), I have some screenshots of Tensorboard logs. This is so that I won't accidentally forget where I left off. 
- Also, my drive is completely full. So, be careful later while continuing. 
- [HuggingFace repo link.](https://huggingface.co/iamTangsang/test-wav2vec2-large-xls-r-300m-nepali-openslr/tree/main)

- September 17, Trained upto 10400 steps. I don't know where the files are. Used 3-4 accounts and all the files are jumbled here and there. So, need to recover.
