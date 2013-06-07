Рівень 1

#Полювання на відьом

__Передмова:__

Цей проект схожий на гру __Полювання на крота__. Очки нараховуються за те, що гравець влучає у відьом, які з'являються на екрані.  Ціль гри отримання якнайбільшої кількості очок за 30 секунд.

##Крок 1:  Створення літаючої відьмиh

1. Створіть новий проект у Скретч.
2. Видаліть спрайт кота і змініть тло(фон) на природу/ліс.
3. Додайте новий спрайт у проект за допомогою відповідної кнопки додавання нових спрайтів (використайте спрайт fantasy/witch1). 

Тепер треба подбати про те, щоб відьма могла рухатись.

1. Додайте лише для цього спрайта змінну  під назвою швидкість. 
На сцені інформація про цю змінну повинна мати вигляд "Образ1 швидкіст".  
Зніміть позначку поряд з блоком швидкості у вкладці Змінні (Variables), щоб він не відображався на сцені. 
Змінна швидкості контролюватиме швидкість руху відьми.  Ми використовуємо змінну, щоб мати змогу змінювати швидкість руху відьми впродовж гри.
2. Відьма повинна почати рухатись із початком гри, тож створимо такий скрипт

```scratch

	коли натиснуто зелений прапорець

	задати швидкість на 5

	завжди

		переміститись на швидкість кроків

	(кінець завжди)
```
		
###Протестуйте свій проект.
__Натисніть на значок із зеленим прапорцем__ і перевірте, що робить відьма.  Чому вона застрягає/зупиняється біля краю екрану?

1. Щоб відьма перестала застрягати/зупинятись нам необхідно прописати скрипт її руху по іншій траєкторії після того, як вона досягне краю екрану.  Це робиться за допомогою блоків з командами "move speed steps" (переміститись на швидкість кроків), "if on edge,bounce" (якщо границя, відбити).

```scratch

	коли натиснуто зелений прапорець

	задати швидкість на 5

	завжди

		переміститись на швидкість кроків

		якщо границя, відбити

	(кінець завжди)
```
1. Щоб відьма перестала хаотично рухатись вверх-вниз, натисніть кнопку __приймати тільки з ліва на право__ у полі інформації про спрайт.

###Протестуйте свій проект.
__Натисніть на значок із зеленим прапорцем.__ 
Чи рухається відьма з однієї сторони в іншу вздовж екрану?

Збережіть свій проект.

###Спробуйте:
__Змінювати величину швидкості, щоб відьма рухалась повільніше або швидше.__

__Як зробити так, щоб відьма набирала більшу швидкість впродовж польоту?__
(Це непросто зробити, тож не хвилюйтесь, якщо цього не зможете.  Впродовж роботи над проектом усе стане зрозумілішим).

##Крок 2: Створення ефекту раптової появи і раптового зникнення відьми.

Щоб зробити гру веселішою, ми зробимо так, щоб відьма раптово з'являлась і щезала.  Зробимо ми це за допомогою скрипта, що виконується одночасно із скриптом, у якому прописано рух відьми.  Цей новий скрипт пропише зникнення відьми з екрану у випадковий момент час, появу її на екрані у випадковий момент часу і постійне повторення цих дій (або повторення їх до завершення гри).

Створіть для відьми такий скрипт:

```scratch

	коли натиснуто зелений прапорець

	завжди

		сховати

		чекати вибрати випадкове від 2 до 5 сек

		сховати

		чекати вибрати випадкове від 3 до 5 сек

	(кінець завжди)
```
###Протестуйте свій проект.
__Натисніть значок із зеленим прапорцем.__ 
Чи рухається відьма з однієї сторони екрану в іншу, час від часу зникаючи і з'являючись?

Збережіть свій проект.

###Спробуйте:
__Змінювати діапазон випадкових чисел.  Що відбувається, коли ви вибираєте дуже великі чи дуже маленькі числа?__
(Чи допомогло це вам зрозуміти, як змусити відьму набирати швидкість впродовж польоту?).

##Крок 3: Створення ефекту зникнення відьми при кліканні на неї.

Щоб зробити цей проект грою, ми повинні придумати, що робити гравцю.  Він повинен клікнути на спрайт відьми, щоб вона зникла. Після клікання на спрайт відьми вона повинна зникнути під звуковий супровід.

1. Із вкладки Звук імпортуйте звук electronic/fairydust (електронні/магічний пил).

2. Додайте такий скрипт для відьми:

```scratch

	коли натиснуто обєкт1

	сховати

	грати звук магічний пил
```
###Протестуйте свій проект.
__Натисніть значок із зеленим прапорцем.__ 

Чи зникає відьма після кліку на неї  супроводі відповідних звуків?

Збережіть свій проект.

##Крок 4: Створення рахунку і таймера для гри.

У нас вже є відьма, а зараз нам треба створити гру! Ми хочемо, щоб при кожному кліку на відьму гравцю нараховувались очки, але при цьому існував ліміт часу для гри.  Скористаємось змінними "score" (рахунок) і "timer" (таймер). 


1. Створіть нову змінну score (рахунок) для всіх спрайтів та змініть скрипт для відьми так, щоб ця змінна збільшувалась на 1 при кліку на відьму.

```scratch

	коли натиснуто обєкт1

	сховати

	грати звук магічний пил

	змінити рахунок на 1
```
2. Перейдіть у поле Сцена і створіть нову змінну (лише для Сцени) "timer" (таймер).  Створіть новий скрипт, який виконується при натисканні значка із зеленим прапорцем, і передбачає установку таймера на 30 секунд і установку рахунку на 0.  Потім використайте команду повтрювати поки, почекати 1 сек, змінити таймер на -1). Ці команди повинні повторюватись, поки таймер не дійде до 0, тоді для завершення гри скористайтесь командою "зупинити все".

```scratch

	коли натиснуто зелений прапорець

	задати таймер на 30

	задати рахунок на 0

	повторити поки таймер = 0

		чекати 1 сек

		змінити таймер на -1

	(кінець повторити)

	зупинити все
```


###Протестуйте свій проект.
__Натисніть на значок із зеленим прапорцем__ 

Збережіть свій проект.

###Спробуйте:
Як можна було б зробити так, щоб відьма впродовж гри набирала швидкість?


__Молодець, створення базової гри завершено, але ще деякі речі, які можна зробити у грі.  Спробуй виконати ці бонусні завдання!__

##Бонусне завдання: додайте більше відьом у гру.

Одна відьма це добре, але більше відьом ще краще! Давай спробуємо створити гру з трьома літаючими відьмами. 
1. Створіть дублікат відьми, натиснувши праву кнопку мишки у полі спрайту. 
2. Для кожної відьми відредагуйте розмір спрайту, щоб усі відьми були різними за величиною.
3. Змініть для кожної відьми змінну швидкості, щоб вони літали на різних швидкостях.
4. Подбайте про те, щоб відьми не рухались по екрану всі разом.

###Протестуйте свій проект
__Натисніть на значок із зеленим прапорцем.__ 

Чи є у грі три відьми, що рухається з однієї сторони екрану в іншу, з'являючись і щезаючи випадковим чином і зникаючи при кліканні на них?

Збережіть свій проект.

###Спробуйте:
1. Яка кількість відьом була б найкращою для гри?  
2. Чи можете ви змінити вигляд відьом?  Ви можете змінювати їх образи або використовувати блоки команд із вкладки Вигляд.m.
3. Чи можете ви зробити так, щоб за кожну з відьом нараховувалась різна кількість очок? Як щодо нараховування 10 очок за відьму з найбільшою (найменшою) швидкістю?

__Молодець! Проект завершено, тепер можна насолоджуватись грою!__
Не забудьте, що грою можна поділитись з друзями та рідними, натиснувши __"Поділитися цим проектом"__ у рядку меню. 