# MedCI: Towards Benchmarking Entity Consistency for Medical Dialogue System

##  Dataset
We introduce a novel dataset annotated by human called MedCI: Entity Consistency Identification in Medical Dialog systems. 

The dialogue data utilized for MedCI is collected from the publicly available MedDG dialogue corpora. 

The dataset contains fine-grained annotations, including Symptom-Disease Inconsistency, Disease-Medicine Inconsistency, and Examination-Disease Inconsistency. We release our dataset together with the code, you can find it in `data.zip`.

The basic format of the dataset is as follows, including multiple rounds of dialogue, knowledge base and related inconsistency annotations (SDI, EDI, MDI)：

```
 {
                "id": "Patients",
                "Sentence": "有点恶心,又有点想拉肚子,而且有点胸闷,和肺炎有关系吗?（男，36岁）",
                "Symptom": [
                    "腹泻",
                    "恶心"
                ],
                "Medicine": [],
                "Examination": [],
                "Attribute": [],
                "Disease": [
                    "肺炎"
                ]
            },
            {
                "id": "Doctor",
                "Sentence": "你好！这种情况多久了？",
                "Symptom": [],
                "Medicine": [],
                "Examination": [],
                "Attribute": [
                    "时长"
                ],
                "Disease": []
            },
            {
                "id": "Patients",
                "Sentence": "胸闷2—3天，以前也经常有，恶心想吐和经常拉肚子。",
                "Symptom": [
                    "腹泻",
                    "恶心",
                    "呕吐"
                ],
                "Medicine": [],
                "Examination": [],
                "Attribute": [],
                "Disease": []
            },
            {
                "id": "Patients",
                "Sentence": "我感冒好了将近二十天左右吧，但是这几年每次感冒好了以后都基本有这种症状。",
                "Symptom": [],
                "Medicine": [],
                "Examination": [],
                "Attribute": [],
                "Disease": [
                    "感冒"
                ]
            },
            {
                "id": "Doctor",
                "Sentence": "有没有发烧。",
                "Symptom": [
                    "发热"
                ],
                "Medicine": [],
                "Examination": [],
                "Attribute": [],
                "Disease": []
            },
            {
                "id": "Patients",
                "Sentence": "没有发烧，每天量好几次都很正常，也很少咳嗽，有时也想咳嗽感觉有痰。有什么问题吗？医生。",
                "Symptom": [
                    "发热",
                    "咳嗽",
                    "有痰"
                ],
                "Medicine": [],
                "Examination": [],
                "Attribute": [],
                "Disease": []
            },
            {
                "id": "Doctor",
                "Sentence": "有接触疑似病例吗。",
                "Symptom": [],
                "Medicine": [],
                "Examination": [],
                "Attribute": [],
                "Disease": []
            },
            {
                "id": "Patients",
                "Sentence": "没有没有去过武汉，附近也没有武汉人。本月8号到19号去了一趟海南三亚，19号晚上回来的。因为感冒好了二十多天了，感觉一直这个状态所以就没有就医，但是这两天肺炎疫情让我感觉心里没底。不过近两年每次冬季感冒好了基本都这个情况。",
                "Symptom": [],
                "Medicine": [],
                "Examination": [],
                "Attribute": [],
                "Disease": [
                    "感冒",
                    "肺炎"
                ]
            },
            {
                "id": "Patients",
                "Sentence": "胸闷感觉有痰，但是不是很想咳嗽。所以感觉更胸闷了。精神状态还可以。就是比较紧张现在的疫情形势。医生您看有什么问题吗？",
                "Symptom": [
                    "咳嗽",
                    "有痰"
                ],
                "Medicine": [],
                "Examination": [],
                "Attribute": [],
                "Disease": []
            },
            {
                "id": "Doctor",
                "Sentence": "那应该和肺炎没什么关系。大家都紧张。你要做的就是宅。",
                "Symptom": [],
                "Medicine": [],
                "Examination": [],
                "Attribute": [],
                "Disease": [
                    "肺炎"
                ]
            }
            
        ]
        "sdi": 0,
        "mdi": 0,
        "edi": 0
    }
```
## Preparation

we provide some pre-trained baselines on MedCI, the packages we used are listed follow:

```
-- scikit-learn==0.23.2
-- numpy=1.19.1
-- pytorch=1.1.0
-- fitlog==0.9.13
-- tqdm=4.49.0
-- sklearn==0.0
-- transformers==3.2.0
```

## How to run it

The script **train.py** acts as a main function to the project, you can run the experiments by the following commands:

```
python -u train.py --cfg MedCI/MedCI_BERT.cfg
```

The parameters we use are configured in the `configure`. If you need to adjust them, you can modify them in the relevant files or append parameters to the command.

`location` is the path to bert or other pre-trained models (e.g., medbert). You can modify this configuration to choose a different pre-trained model.

