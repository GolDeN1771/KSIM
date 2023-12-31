## Комп'ютерні системи імітаційного моделювання
## СПм-22-4, **Яценко Ігор Станіславович**
### Лабораторна робота №**3**. Використання засобів обчислювального интелекту для оптимізації імітаційних моделей

<br>

### Варіант 24(11), модель у середовищі NetLogo:
[Autumn](https://www.netlogoweb.org/launch#http://www.netlogoweb.org/assets/modelslib/Sample%20Models/Biology/Autumn.nlogo)

<br>

#### Вербальний опис моделі:
- **[Вербальний опис моделі лабораторна робота №1](https://github.com/GolDeN1771/KSIM/blob/main/lb1/lab1.md)**

<br>

### Налаштування середовища BehaviorSearch:

**Обрана модель**:
<pre>
C:\Users\yatse\Desktop\NetLogo 6.4.0\models\Sample Models\Biology\Autumn.nlogo
</pre>
**Параметри моделі** (вкладка Model):  
*Параметри та їх можливі діапазони були **автоматично** вилучені середовищем BehaviorSearch із вибраної імітаційної моделі, для цього є кнопка «Завантажити діапазони параметрів із інтерфейсу моделі»*:
<pre>
["number-of-leaves" 600]
["wind-factor" [0 1 10]]
["temperature" [0 1 40]]
["rain-intensity" [0 1 30]]
["sun-intensity" [0 1 100]]
["start-sugar-mean" [0 1 100]]
["start-sugar-stddev" [0 1 50]]
["leaf-display-mode" "solid" "chlorophyll" "water" "sugar" "carotene" "anthocyanin" "attachedness"]
</pre>
Використовувана **міра**:  
Для фітнес-функції *(вона ж функція пристосованості або цільова функція)* було обрано **значення кількості листя**. Саме кількість тактів визначає успішність симуляції, адже чим довше проводилася симуляція тим краще були підібрані керуючі параметри та тим довше листя залишалися на дереві. Вираз для її розрахунку вказано у параметрі "**Measure**":
<pre>
count leaves
</pre> 
Кількість тактів повинна враховуватися **у кінці** симуляції тривалістю 200 тактів, починаючи з 0 такту симуляції.  
Параметр зупинки за умовою ("**Stop if**") у разі не використовувався.  
Іншими словами, завданням є знаходження таких параметрів, за яких досягається найвищий показник листя на дереві.
Загальний вигляд вкладки налаштувань параметрів моделі:  

![Вкладка налаштувань параметрів моделі](model.png)

**Налаштування цільової функції** (вкладка Search Objective):  
Метою підбору параметрів імітаційної моделі є **максимізація** значення – це вказано через параметр "**Goal**" зі значенням **Maximize Fitness**. Враховуватися повинно саме кінцеве значення. Для цього у параметрі "**Collected measure**", що визначає спосіб обліку значень обраного показника, вказано **AT_FINAL_STEP**.  
Щоб уникнути викривлення результатів через випадкові значення, що використовуються в логіці самої імітаційної моделі, **кожна симуляція повторюється по 10 разів**, результуюче значення розраховується як **середнє арифметичне**. 
Загальний вигляд вкладки налаштувань цільової функції:  

![Вкладка налаштувань цільової функції](search_obj.png)

**Налаштування алгоритму пошуку** (вкладка Search Algorithm):  
Загальний вид вкладки налаштувань алгоритму пошуку:  

![Вкладка налаштувань пошуку](search_alg.png)

<br>

### Результати використання BehaviorSearch:
Діалогове вікно запуску пошуку:  

![Вікно запуску пошуку](run_option.png)

Результат пошуку параметрів імітаційної моделі, використовуючи **генетичний алгоритм**:  

![Результати пошуку за допомогою ГА](standardga.png)

Результат пошуку параметрів імітаційної моделі, використовуючи **випадковий пошук**:  

![Результати випадкового пошуку](random.png)

- У данній лабораторній роботі я дослідив використання засобів обчислювального інтелекту для оптимізації імітаційних моделей у програмі BehaviorSearch.
- Провів 2 дослідження за допомогою генетичного алгоритму та випадкового пошуку. Алгоритм випадкового пошуку виявився набагато швидшим.
