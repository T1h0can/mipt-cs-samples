# Правила написания контрольной работы

* **Можно** пользоваться любыми печатными материалами, принесёнными с собой. Можно читать маны, а также гуглить и даже
  списывать со StackOverflow.
* **Запрещается** пользоваться телефонами, общаться друг с другом, использовать 
  социальные сети/мессенджеры/чаты/и-вот-это-вот-всё. За несоблюдение правил студент сразу же удаляется с зачёта —
  предупреждений не будет. Любая попытка списать готовое решение закончится пересдачей, на которой максимум,
  что можно будет получить — 3 балла. Все вопросы (даже если вам внезапно нужна ручка) — только к преподавателю.
* К сдаче принимаются только те программы, которые компилируются. Если программа не собирается, то считается,
  что задача не решена.
* Критерий оценивания: одна решённая задач — «удовлетворительно», две решённые задачи — «хорошо». Конкретный балл
  зависит от того, как написана программа.
* Время на решение задач — до 11:00. После этого начинается сдача. При отсутствии желающих сдавать таковые будут
  выбираться в произвольном порядке — никаких «мне ещё буквально пять минут» не будет.
* Прокси для доступа в интернет — http://10.55.163.88:3128.

# Задача 1 — первая половина семестра :: системное программирование

В каждом варианте предполагается написание ровно одной программы: ответом является **один** cpp-файл, который
компилируется в **один** бинарный файл. Все программы предполагают создание нескольких потоков или процессов.
Если по условию задачи процессы/потоки выполняют разные действия, то должен быть предусмотрен способ запустить
программу в соответствующем режиме (для этого разрешается использовать любые подходы).

## Вариант 1

В одной стране недавно построили мост. Строили долго и упорно, потому что этот мост был очень нужен.
Проблема в том, что не все деньги пошли туда, куда надо, поэтому мост имеет весьма слабую пропускную способность —
по нему могут ехать одновременно не больше N машин, суммарная масса которых не должна превышать M. Из-за этого
каждый день перед мостом собирается огромное количество машин, которые хотят через этот мост проехать. Водители ведут
себя нагло и лезут без очереди, но ограничения всё же соблюдают — никто не хочет, чтобы мост разрушился,
когда по нему едут.

Вам заданы ограничения M и N, а также последовательность целых чисел mᵢ — массы автомобилей, которые хотят проехать по мосту.
Смоделируйте процесс проезда по мосту, представив каждую машину в виде процесса.


## Вариант 2

N математиков играют в интересную и увлекательную игру. Ну, по крайней мере они считаю эту игру интересной и
увлекательной. Суть игры заключается в следующем. Сначала они выбирают произвольное положительное число.
Затем первый вычитает из этого числа 1, второй вычитает из оставшегося числа 2 и т.д. Когда N-й математик вычтет из
числа N, ход снова переходит к первому. На этот раз он вычитает N+1, затем второй N+2 и т.д. Игра длится до тех пор,
пока после хода очередного игрока число не станет отрицательным.

Вам задано число N. Смоделируйте ход интересной и увлекательной игры, представив каждого игрока отдельным потоком.

## Вариант 3

В больнице проходит медосмотр. Каждому пациенту нужно пройти N врачей. Конечно же записаться на точное время нельзя,
поэтому приходится сидеть в очереди. Поскольку все пациенты хотят побыстрее пройти медосмотр,
то изначально они сидят в очереди к разным врачам. После осмотра пациента i-й врач отправляет пациента к i+1-му врачу.
Когда пациент посетил всех врачей, он уходит из больницы с приятным ощущением, что не зря потратил время.

Вам задана последовательность чисел aᵢ, каждый элемент которой равняется номеру врача, в очереди к которому сидит
i-й пациент. Смоделируйте процесс прохождения очереди пациентами, представив каждого врача отдельным процессом.

# Задача 2 — вторая половина семестра :: MPI

Написать параллельную программу, которая вычисляет ∫sin(x)/ln(x)\*dx по отрезку [2; ζ], где ζ определяется по-разному
для каждого варианта.

## Вариант 1

ζ=q/ln(π), где q — среднее значение идентификаторов всех процессов, запущенных в рамках расчёта.

## Вариант 2

ζ=∛q, где q —  минимальное значение среди идентификаторов всех процессов, запущенных в рамках расчёта.

## Вариант 3

ζ — q/sin(ℯ), q — сумма значений идентификаторов всех процессов, запущенных в рамках расчёта.
