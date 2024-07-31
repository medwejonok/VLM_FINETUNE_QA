# Обучение VLM на задачу QA
> Денис Маликов

## 1. Выбрать существующую VLM:
   Я выбрал Moondream2 - https://huggingface.co/vikhyatk/moondream2
   <br/><br/>
   ![image](https://github.com/user-attachments/assets/8ee84a67-3e86-4352-a0f3-5b82ff791722)    
   <br/><br/>
   Модель создана для задачи VLM.
   <br/><br/>
## 2. Выберите датасет:
Я выбрал датасет https://huggingface.co/datasets/listen2you002/ChartLlama-Dataset
Он простой в понимании и прекрасно подходит для задачи VQA.
 
К каждой картинке есть диалог с нейросетью.

Обучающий датасет состоит из 1054 вопросов для тренировки и 118 вопросов для теста.

## 3. Дообучить модель на этих данных. 
Весь процесс обучения я изложил в **pipeline.ipynb**

## 4. Выберите метрику для вашей задачи и объясните ее выбор.
Для задачи QA я выбрал такие метрики:     
**Точность (Accuracy)**: Процент вопросов, на которые модель ответила правильно.    
**F1-мера**: Среднее гармоническое между точностью и полнотой.    
**ROUGE**: Метрика, которая измеряет совпадение слов между ответом модели и эталонным ответом.    

## Итоговые метрики

**Метрики обычной модели**:    
Точность: 0.0    
F1-мера: 0.0       
ROUGE-1: {'r': 0.12017594916754581, 'p': 0.03504597827353245, 'f': 0.047154155157596966}      
ROUGE-2: {'r': 0.023289315726290515, 'p': 0.009176020940726823, 'f': 0.011400834649175393}      
ROUGE-L: {'r': 0.11731116689099882, 'p': 0.03236279973896073, 'f': 0.04460934638441449}}      
<br/>
<br/>
**Метрики обученной модели**:    
Точность: 0.3949579831932773      
F1-мера: 0.39495798319327724      
ROUGE-1: {'r': 0.44676325075484735, 'p': 0.4451853468660191, 'f': 0.4433325794435508}        
ROUGE-2: {'r': 0.05921368547418967, 'p': 0.059803921568627454, 'f': 0.059323729035511356}      
ROUGE-L: {'r': 0.4459993088144349, 'p': 0.4437847866419295, 'f': 0.44234394869713456}}  
## Визуальное сравнение модели
![image](https://github.com/user-attachments/assets/b88b99ce-fa79-4b6b-943a-8257bd34253b)
![image](https://github.com/user-attachments/assets/c83adbe6-8f87-410f-9410-e4fd25ba3069)


# Вывод
Результаты fine-tune модели VLM на задачу QA показывают улучшение по сравнению с обычной моделью. 

Положительные изменения:

Точность и F1-мера: Значительное повышение точности и F1-меры (с 0.0 до 0.39) говорит о том, что модель действительно научилась решать задачу QA. Это большой шаг вперед.
ROUGE: Значительное повышение ROUGE-1, ROUGE-2 и ROUGE-L подтверждает, что ответы модели стали более похожи на релевантные ответы на вопросы.
