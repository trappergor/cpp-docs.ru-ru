---
title: Таблица соответствия Microsoft Visual C++ стандартам языка
description: Таблица изменений соответствия Microsoft C++ в зависимости от версии Visual Studio.
ms.date: 03/17/2020
ms.technology: cpp-language
ms.assetid: 475da6e9-0d78-4b4e-bd23-f41c406c4efe
author: corob-msft
ms.author: corob
ms.openlocfilehash: 8a5ffb5b3ab4bc80cb200b41752b19d1c958ece6
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079363"
---
# <a name="microsoft-c-language-conformance-table"></a>Таблица соответствия Microsoft Visual C++ стандартам языка

Работа над соблюдением стандартов для компилятора Microsoft C++ в Visual Studio (MSVC) еще ведется. Ниже приведена сводка по соответствию языка C++ и библиотеки стандарту ISO по версиям Visual Studio. Каждое название функции компилятора и стандартной библиотеки является ссылкой на документ по C++ стандарта ISO, где находится ее описание (если функция доступна на момент публикации). В столбце **поддерживаемых** версий перечислены версии Visual Studio, в которых впервые появилась поддержка функции.

Дополнительные сведения об улучшениях соответствия MSVC в Visual Studio 2017 или Visual Studio 2019 см. в статье [Улучшения соответствия C++ в Visual Studio](cpp-conformance-improvements.md). Список других изменений см. в статье [Новые возможности C++ в Visual Studio](what-s-new-for-visual-cpp-in-visual-studio.md). Сведения об изменениях соответствия в более ранних версиях см. в статье [Критические изменения в Visual C++](../porting/visual-cpp-change-history-2003-2015.md) и [Visual C++ What's New 2003 through 2015](../porting/visual-cpp-what-s-new-2003-through-2015.md)(Новые возможности Visual C++ в версиях 2003–2015). Последние новости от команды разработчиков C++ см. в [блоге команды разработчиков C++](https://devblogs.microsoft.com/cppblog/).

> [!NOTE]
> Принципы работы с двоичными файлами в Visual Studio 2015, Visual Studio 2017 и Visual Studio 2019 существенно не изменились. Дополнительные сведения см. в статье [C++ binary compatibility between Visual Studio 2015, 2017, and 2019](../porting/binary-compat-2015-2017.md) (Совместимость C++ на уровне двоичного кода между Visual Studio 2015, 2017 и 2019).

## <a name="compiler-features"></a>Функции компилятора

|  |  |
|--|--|
| __Основные возможности языка C++03/11__ | __Поддерживается__ |
| &nbsp;&nbsp;В любом другом месте | VS 2015 <sup>[A](#note_A)</sup> |
| &nbsp;&nbsp;Двухэтапный поиск по имени | VS 2017 15.7 <sup>[B](#note_B)</sup> |
| &nbsp;&nbsp;[N2634 Выражение SFINAE](https://wg21.link/N2634) | VS 2017 15.7 |
| &nbsp;&nbsp;[N1653 Препроцессор C99](https://wg21.link/N1653) | Частично <sup>[C](#note_C)</sup> |
| __Основные возможности языка C++14__ | __Поддерживается__ |
| &nbsp;&nbsp;[N3323 Настраиваемое контекстное преобразование](https://wg21.link/N3323) | VS 2013 |
| &nbsp;&nbsp;[N3472 Двоичные литералы](https://wg21.link/N3472) | VS 2015 |
| &nbsp;&nbsp;[N3638 Возвращаемые типы auto и decltype(auto)](https://wg21.link/n3638) | VS 2015 |
| &nbsp;&nbsp;[N3648 Захват при инициализации](https://wg21.link/n3648) | VS 2015 |
| &nbsp;&nbsp;[N3649 Универсальные лямбда-выражения](https://wg21.link/n3649) | VS 2015 |
| &nbsp;&nbsp;[N3760 Атрибут \[\[deprecated\]\]](https://wg21.link/n3760) | VS 2015 |
| &nbsp;&nbsp;[N3778 Освобождение с указанием размера](https://wg21.link/n3778) | VS 2015 |
| &nbsp;&nbsp;[N3781 Разделители цифр](https://wg21.link/n3781) | VS 2015 |
| &nbsp;&nbsp;[N3651 Шаблоны переменных](https://wg21.link/n3651) | VS 2015.2 |
| &nbsp;&nbsp;[N3652 Расширенный constexpr](https://wg21.link/n3652) | VS 2017 15.0 |
| &nbsp;&nbsp;[N3653 Инициализаторы элементов по умолчанию для агрегатов](https://wg21.link/n3653) | VS 2017 15.0 |
| __Основные возможности языка C++17__ | __Поддерживается__ |
| &nbsp;&nbsp;[N4086 Удаление триграфов](https://wg21.link/n4086) | VS 2010 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N3922 Новые правила для автоматического использования с braced-init-lists](https://wg21.link/n3922) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4051 Имя типа в параметрах шаблона](https://wg21.link/n4051) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4266 Атрибуты пространств имен и перечислителей](https://wg21.link/n4266) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4267 Знаковые литералы u8](https://wg21.link/n4267) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4230 Определение вложенных пространств имен](https://wg21.link/n4230) | VS 2015.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[N3928 Краткие статические операции static_assert](https://wg21.link/n3928) | VS 2017 15.0 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0184R0 Обобщенный цикл for на основе диапазона](https://wg21.link/p0184r0) | VS 2017 15.0 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0188R1 Атрибут \[\[fallthrough\]\]](https://wg21.link/p0188r1) | VS 2017 15.0 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0001R1 Удаление ключевого слова register](https://wg21.link/p0001r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0002R1 Удаление operator++ для типа bool](https://wg21.link/p0002r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0018R3 Захват *this по значению](https://wg21.link/p0018r3) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0028R4 Использование пространств имен атрибутов без повторения](https://wg21.link/p0028r4) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0061R1 \_\_has_include](https://wg21.link/p0061r1) | VS 2017 15.3 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0138R2 Прямая инициализация списком фиксированных перечисляемых типов из целых чисел](https://wg21.link/p0138r2) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0170R1 Лямбда-выражения constexpr](https://wg21.link/p0170r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0189R1 Атрибут \[\[nodiscard\]\]](https://wg21.link/p0189r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0212R1 Атрибут \[\[maybe_unused\]\]](https://wg21.link/p0212r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0217R3 Структурированные привязки](https://wg21.link/p0217r3) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0292R2 Операторы if в constexpr](https://wg21.link/p0292r2) | VS 2017 15.3 <sup>[D](#note_D)</sup> |
| &nbsp;&nbsp;[P0305R1 Операторы выбора с инициализаторами](https://wg21.link/p0305r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0245R1 Шестнадцатеричные литералы с плавающей запятой](https://wg21.link/p0245r1) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[N4268 Разрешение дополнительных аргументов шаблона, не являющихся типом](https://wg21.link/n4268) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[N4295 Выражения свертывания](https://wg21.link/n4295) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0003R5 Удаление динамических спецификаций исключений](https://wg21.link/p0003r5) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0012R1 Добавление noexcept к системе типов](https://wg21.link/p0012r1) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0035R4 Избыточное выделение динамической памяти](https://wg21.link/p0035r4) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0386R2 Встроенные переменные](https://wg21.link/p0386r2) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0522R0 Сопоставление параметров шаблона с совместимыми аргументами](https://wg21.link/p0522r0) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0036R0 Удаление некоторых пустых унарных свертываний](https://wg21.link/p0036r0) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[N4261 Исправление преобразований квалификации](https://wg21.link/n4261) | VS 2017 15.7 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0017R1 Расширенная агрегатная инициализация](https://wg21.link/p0017r1) | VS 2017 15.7 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0091R3 Выведение аргументов шаблонов для шаблонов классов](https://wg21.link/p0091r3)<br/>&nbsp;&nbsp;[P0512R0 Проблемы с выведением аргумента шаблона класса](https://wg21.link/p0512r0) | VS 2017 15.7 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0127R2 Объявление параметров шаблона, не являющихся типами, с auto](https://wg21.link/p0127r2) | VS 2017 15.7 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0135R1 Гарантированный пропуск копирования](https://wg21.link/p0135r1) | VS 2017 15.6 |
| &nbsp;&nbsp;[P0136R1 Перефразирование наследования конструкторов](https://wg21.link/p0136r1) | VS 2017 15.7 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0137R1 std::launder](https://wg21.link/p0137r1) | VS 2017 15.7 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0145R3 Уточнение порядка вычисления выражений](https://wg21.link/p0145r3)<br/>&nbsp;&nbsp;[P0400R0 Порядок вычисления аргументов функции ](https://wg21.link/p0400r0) | VS 2017 15.7 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0195R2 Упаковка расширений в объявлениях using](https://wg21.link/p0195r2) | VS 2017 15.7 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0283R2 Пропуск нераспознанных атрибутов](https://wg21.link/p0283r2) | VS 2015 <sup>[14](#note_14)</sup> |
| __Основные возможности языка C++17 (сообщения о дефектах)__ | __Поддерживается__ |
| &nbsp;&nbsp;[P0702R1 Исправление выведения шаблона аргумента класса для конструкторов списка инициализаторов](https://wg21.link/p0702r1) | VS 2017 15.7 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0961R1 Ослабление правил поиска точки настройки структурированных привязок](https://wg21.link/p0961r1) | VS 2019 16.0 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0969R0 Разрешение структурированных привязок для доступных членов](https://wg21.link/p0969r0) | VS 2019 16.0 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0588R1 Упрощение неявного захвата в лямбда-выражении](https://wg21.link/p0588r1) | VS 2019 16.4<sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P1771R1. \[\[nodiscard\]\] для конструкторов](https://wg21.link/p1771r1) | VS 2019 16.4<sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P1825R0. Объединенная формулировка для P0527R1 и P1155R3, дополнительные неявные перемещения](https://wg21.link/p1825r0) | VS 2019 16.4<sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0929R2 Проверка на наличие типов абстрактного класса](https://wg21.link/P0929R2) | Нет |
| &nbsp;&nbsp;[P0962R2 Ослабление правил поиска точки настройки выражений for, основанных на диапазоне](https://wg21.link/p0962r1) | Нет |
| &nbsp;&nbsp;[P0859R0 CWG 1581: когда определяются функции-члены constexpr](https://wg21.link/p0859r0) | Нет |
| &nbsp;&nbsp;[P1009R2 Определение размера массива в новых выражениях](https://wg21.link/P1009R2) | Нет |
| &nbsp;&nbsp;[P1286R2 Альтернативное решение для CWG DR1778](https://wg21.link/P1286R2) | Нет |
| __Основные возможности языка C++20__ | __Поддерживается__ |
| &nbsp;&nbsp;[P0704R1 Исправления указателей элементов const lvalue, проверенных по ссылке](https://wg21.link/p0704r1) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P1041R4 Использование char16_t и char32_t в формате UTF-16 и UTF-32](https://wg21.link/P1041R4) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P1330R0 Изменение активного элемента объединения внутри constexpr](https://wg21.link/P1330R0) | VS 2017 15.0 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0972R0 noexcept для \<chrono> zero(), min(), max()](https://wg21.link/P0972R0) | VS 2017 15.7 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0515R3 Оператор трехстороннего сравнения (космический корабль) <=>](https://wg21.link/P0515R3) | VS 2019 16.0 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0941R2 Макросы тестирования функций](https://wg21.link/P0941R2) | VS 2019 16.0 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P1008R1 Запрет агрегирования с объявленными пользователем конструкторами](https://wg21.link/P1008R1) | VS 2019 16.0 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0329R4 Назначенный конструктор инициализации](https://wg21.link/p0329r4) | VS 2019 16.1 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0846R0 ADL и шаблоны функций, которые не отображаются](https://wg21.link/P0846R0) | VS 2019 16.1 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0409R2 Разрешение в лямбда-выражении захвата объекта\[=, this\]](https://wg21.link/p0409r2) | VS 2019 16.2<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0428R2 Знакомый синтаксис шаблона для универсальных лямбда-выражений](https://wg21.link/p0428r2) | VS 2019 16.2<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0624R2 Конструируемые и назначаемые лямбда-выражения по умолчанию](https://wg21.link/P0624R2) | VS 2019 16.2<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0780R2 Разрешение раскрытия пакета в лямбда-выражении init-capture](https://wg21.link/P0780R2) | VS 2019 16.2<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0806R2 Не рекомендуется неявный захват this с помощью \[=\]](https://wg21.link/P0806R2) | VS 2019 16.2<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1120R0 Улучшения согласованности <=> и других операторов сравнения](https://wg21.link/P1120R0) | VS 2019 16.2<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1185R2 \<=\> != ==](https://wg21.link/P1185R2) | VS 2019 16.2<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0734R0 Основные понятия ](https://wg21.link/P0734R0) | VS 2019 16.3<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0857R0 Исправление функциональных пробелов в ограничениях](https://wg21.link/P0857R0) | VS 2019 16.3<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1084R2 Текущая недостаточность требований к типу возврата](https://wg21.link/P1084R2) | VS 2019 16.3<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0892R2 Условно явный конструктор](https://wg21.link/P0892R2) | VS 2019 16.4<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1091R3 Расширение структурированных привязок до их подобия с объявлениями переменных](https://wg21.link/P1091R3) | VS 2019 16.4<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1099R5. Использование перечисления](https://wg21.link/P1099R5) | VS 2019 16.4<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1186R3. Случаи фактического использования \<=>](https://wg21.link/P1186R3) | VS 2019 16.4<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1630R1. Для космического корабля необходима настройка](https://wg21.link/P1630R1) | VS 2019 16.4<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0306R4 Добавление \_\_VA_OPT\_\_ для пропуска и удаления запятых](https://wg21.link/P0306R4) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0614R1 Циклы for на основе диапазона с инициализаторами](https://wg21.link/P0614R1) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0683R1 Инициализатор элементов по умолчанию для битовых полей](https://wg21.link/P0683R1) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1002R1 Блоки try-catch в функциях constexpr](https://wg21.link/P1002R1) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1161R3 Не рекомендуется использовать оператор "запятая" в выражениях индексации](https://wg21.link/P1161R3) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1301R4 \[\[nodiscard("message")\]\]](https://wg21.link/P1301R4) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1703R1 Для распознавания импортов блока заголовка требуется полная предварительная обработка](https://wg21.link/P1703R1) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1946R0 Разрешение сравнений по значениям по умолчанию](https://wg21.link/P1946R0) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0641R2 Несовпадение const с конструктором копирования по умолчанию](https://wg21.link/P0641R2) | Partial |
| &nbsp;&nbsp;[P0912R5 Сопрограммы](https://wg21.link/P0912R5) | Partial |
| &nbsp;&nbsp;[P1103R3 Модули](https://wg21.link/P1103R3) | Partial |
| &nbsp;&nbsp;[P0315R4 Разрешение лямбда-выражений в невычисляемых контекстах](https://wg21.link/P0315R4) | Нет |
| &nbsp;&nbsp;[P0388R4 Разрешение преобразований в массивы неизвестной привязки](https://wg21.link/P0388R4) | Нет |
| &nbsp;&nbsp;[P0479R5 Атрибуты \[\[likely\]\] и \[\[unlikely\]\]](https://wg21.link/P0479R5) | Нет |
| &nbsp;&nbsp;[P0634R3 Долой typename!](https://wg21.link/P0634R3) | Нет |
| &nbsp;&nbsp;[P0692R1 Послабление проверки доступа для специализаций](https://wg21.link/P0692R1) | Нет |
| &nbsp;&nbsp;[P0722R3 Delete небольшого размера для классов различных размеров](https://wg21.link/P0722R3) | Нет |
| &nbsp;&nbsp;[P0732R2 Типы классов в параметрах шаблона, не являющегося типом](https://wg21.link/P0732R2) | Нет |
| &nbsp;&nbsp;[P0735R1 Взаимодействие memory_order_consume с последовательностями выпуска](https://wg21.link/P0735R1) | Нет |
| &nbsp;&nbsp;[P0784R7 Больше контейнеров constexpr](https://wg21.link/P0784R7) | Нет |
| &nbsp;&nbsp;[P0840R2 Атрибут \[\[no_unique_address\]\]](https://wg21.link/P0840R2) | Нет |
| &nbsp;&nbsp;[P0848R3 Условно тривиальные специальные функции-члены](https://wg21.link/P0848R3) | Нет |
| &nbsp;&nbsp;[P0960R3 Разрешение инициализации агрегатов из списка значений в скобках](https://wg21.link/P0960R3) | Нет |
| &nbsp;&nbsp;[P1064R0 Разрешение вызовов виртуальных функций в константных выражениях](https://wg21.link/P1064R0) | Нет |
| &nbsp;&nbsp;[P1073R3 Немедленные функции](https://wg21.link/P1073R3) | Нет |
| &nbsp;&nbsp;[P1094R2 Вложенные встроенные пространства имен](https://wg21.link/P1094R2) | Нет |
| &nbsp;&nbsp;[P1139R2 Проблемы формулирования адреса, связанные с ISO 10646](https://wg21.link/P1139R2) | Нет |
| &nbsp;&nbsp;[P1141R2 Еще один подход для ограниченных объявлений](https://wg21.link/P1141R2) | Нет |
| &nbsp;&nbsp;[P1143R2 constinit](https://wg21.link/P1143R2) | Нет |
| &nbsp;&nbsp;[P1152R4 Нерекомендуемые переменные](https://wg21.link/P1152R4) | Нет |
| &nbsp;&nbsp;[P1236R1 Представление целых чисел со знаком в представлении в виде дополнения](https://wg21.link/P1236R1) | Нет |
| &nbsp;&nbsp;[P1327R1 Разрешение использования dynamic_cast, полиморфного typeid в константных выражениях](https://wg21.link/P1327R1) | Нет |
| &nbsp;&nbsp;[P1331R2 Разрешение тривиальной инициализации по умолчанию в контекстах constexpr](https://wg21.link/P1331R2) | Нет |
| &nbsp;&nbsp;[P1353R0 Отсутствующие макросы тестирования функций](https://wg21.link/P1353R0) | Нет |
| &nbsp;&nbsp;[P1381R1 Захват указателей на структурированные привязки](https://wg21.link/P1381R1) | Нет |
| &nbsp;&nbsp;[P1452R2 При неоднородной семантике требований return-type](https://wg21.link/P1452R2) | Нет |
| &nbsp;&nbsp;[P1616R1 Использование неограниченных TTP с ограниченными шаблонами](https://wg21.link/P1616R1) | Нет |
| &nbsp;&nbsp;[P1668R1 Разрешение неоцененной встроенной сборки в функциях constexpr](https://wg21.link/P1668R1) | Нет |
| &nbsp;&nbsp;[P1766R1 Устранение незначительных неполадок модулей](https://wg21.link/P1766R1) | Нет |
| &nbsp;&nbsp;[P1811R0 Ослабление ограничений на переопределение для надежности повторного экспорта](https://wg21.link/P1811R0) | Нет |
| &nbsp;&nbsp;[P1814R0 CTAD для шаблонов псевдонимов](https://wg21.link/P1814R0) | Нет |
| &nbsp;&nbsp;[P1816R0 CTAD для агрегатов](https://wg21.link/P1816R0) | Нет |
| &nbsp;&nbsp;[P1874R1 Динамический порядок инициализации нелокальных переменных в модулях](https://wg21.link/P1874R1) | Нет |
| &nbsp;&nbsp;[P1907R1 Несогласованности с параметрами шаблона, не являющимися типами](https://wg21.link/P1907R1) | Нет |
| &nbsp;&nbsp;[P1971R0 Основные изменения для комментариев NB, принятые на встрече в ноябре 2019 г. (Белфаст)](https://wg21.link/P1971R0) | Нет |
| &nbsp;&nbsp;[P1972R0 US105 Проверка выполнения ограничений для нешаблонных объектов при создании указателя на функцию](https://wg21.link/P1972R0) | Нет |
| &nbsp;&nbsp;[P1975R0 Исправление описания инициализации агрегата в скобках](https://wg21.link/P1975R0) | Нет |
| &nbsp;&nbsp;[P1979R0 Разрешение в US086](https://wg21.link/P1979R0) | Нет |
| &nbsp;&nbsp;[P1980R0 CA096: сопоставление объявлений для независимых предложений requires](https://wg21.link/P1980R0) | Нет |

## <a name="standard-library-features"></a>Функции стандартной библиотеки

|  |  |
|--|--|
| __Функции стандартной библиотеки C++20__ | __Поддерживается__ |
| &nbsp;&nbsp;[P0809R0 Сравнение неупорядоченных контейнеров](https://wg21.link/p0809r0) | VS 2010 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0858R0 Требования к итератору constexpr](https://wg21.link/p0858r0) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0777R1 Отказ от излишнего использования decay](https://wg21.link/p0777r1) | VS 2017 15.7 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P1164R1. Повышение удобства работы с функцией create_directory()](https://wg21.link/P1164R1) | VS 2019 16.0 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0550R2 remove_cvref](https://wg21.link/p0550r2) | VS 2019 16.0 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0318R1 unwrap_reference, unwrap_ref_decay](https://wg21.link/p0318r1) | VS 2019 16.1 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0457R2 Starts_with()/ends_with() для basic_string/basic_string_view](https://wg21.link/p0457r2) | VS 2019 16.1 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0458R2 contains() для упорядоченных и неупорядоченных ассоциативных контейнеров](https://wg21.link/p0458r2) | VS 2019 16.1 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0646R1 Возвращаемый size_type для list/forward_list remove()/remove_if()/unique()](https://wg21.link/p0646r1) | VS 2019 16.1 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0769R2 shift_left(), shift_right()](https://wg21.link/p0769r2) | VS 2019 16.1 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0887R1 type_identity](https://wg21.link/p0887r1) | VS 2019 16.1 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0020R6 atomic\<float>, atomic\<double>, atomic\<long double>](https://wg21.link/p0020r6) | VS 2019 16.2<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0463R1 Порядок байтов](https://wg21.link/p0463r1) | VS 2019 16.2<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0482R6 char8_t: тип для символов и строк UTF-8](https://wg21.link/P0482R6) | VS 2019 16.2<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0600R1 \[\[nodiscard\]\] для STL, часть 1](https://wg21.link/p0600r1) | VS 2019 16.2<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0653R2 to_address()](https://wg21.link/p0653r2) | VS 2019 16.2<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0754R2 \<version>](https://wg21.link/p0754r2) | VS 2019 16.2<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0771R1 noexcept для конструктора перемещения std::function](https://wg21.link/P0771R1) | VS 2019 16.2<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0487R1 Исправление operator>>(basic_istream&, CharT*)](https://wg21.link/P0487R1) | VS 2019 16.3<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0616R0 Использование move() в \<numeric>](https://wg21.link/p0616r0) | VS 2019 16.3<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0758R1 is_nothrow_convertible](https://wg21.link/P0758R1) | VS 2019 16.3<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0898R3 Основные понятия стандартной библиотеки](https://wg21.link/P0898R3) | VS 2019 16.3<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0919R3 Разнородный поиск для неупорядоченных контейнеров](https://wg21.link/P0919R3) | VS 2019 16.3<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1754R1. Переименование концепций для использования стандартного регистра](https://wg21.link/P1754R1) | VS 2019 16.4<sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0325R4 to_array из LFTS с обновлениями](https://wg21.link/P0325R4) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0340R3 underlying_type с поддержкой SFINAE](https://wg21.link/P0340R3) | VS 2019 16.5 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0356R5 bind_front()](https://wg21.link/P0356R5) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0439R0 Класс перечисления memory_order](https://wg21.link/p0439r0) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0553R4 \<bit> Функции поворота и подсчета](https://wg21.link/P0553R4) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0556R3 \<bit> ispow2(), ceil2(), floor2(), log2p1()](https://wg21.link/P0556R3) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0595R2 is_constant_evaluated()](https://wg21.link/P0595R2) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0631R8 \<numbers> Математические константы](https://wg21.link/P0631R8) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0738R2 Очистка istream_iterator](https://wg21.link/P0738R2) | VS 2019 16.5 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0767R1 Отказ от использования is_pod](https://wg21.link/P0767R1) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0966R1 Функция string::reserve() не должна сжимать](https://wg21.link/P0966R1) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1209R0 erase_if(), erase()](https://wg21.link/P1209R0) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1227R2 std::ssize() со знаком, span::size() без знака](https://wg21.link/P1227R2) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1355R2 Суженный контракт для ceil2()](https://wg21.link/P1355R2) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1357R1 is_bounded_array, is_unbounded_array](https://wg21.link/P1357R1) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1612R1 Перемещение порядка байтов в \<bit>](https://wg21.link/P1612R1) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1651R0 bind_front() не должен разворачивать reference_wrapper](https://wg21.link/P1651R0) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1690R1 Уточнение разнородного поиска для неупорядоченных контейнеров](https://wg21.link/P1690R1) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1902R1 Отсутствующие макросы тестирования функций 2017–2019 г.](https://wg21.link/P1902R1) | VS 2019 16.5 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0019R8 atomic_ref](https://wg21.link/P0019R8) | Нет |
| &nbsp;&nbsp;[P0053R7 \<syncstream>](https://wg21.link/p0053r7)<br/>&nbsp;&nbsp;[P0753R2 Манипуляторы osyncstream](https://wg21.link/p0753r2) | Нет |
| &nbsp;&nbsp;[P0122R7 \<span>](https://wg21.link/p0122r7) | Нет |
| &nbsp;&nbsp;[P0202R3 constexpr для \<algorithm> и exchange()](https://wg21.link/p0202r3) | Нет |
| &nbsp;&nbsp;[P0339R6 polymorphic_allocator<>](https://wg21.link/P0339R6) | Нет |
| &nbsp;&nbsp;[P0355R7 \<chrono > для календарей и часовых поясов](https://wg21.link/p0355r7) | Нет |
| &nbsp;&nbsp;[P0357R3 Поддержка неполных типов в reference_wrapper](https://wg21.link/P0357R3) | Нет |
| &nbsp;&nbsp;[P0415R1 constexpr для \<complex> (повторно)](https://wg21.link/p0415r1) | Нет |
| &nbsp;&nbsp;[P0475R1 Гарантированный пропуск копирования для конструктора кусочно-заданной функции](https://wg21.link/P0475R1) | Нет |
| &nbsp;&nbsp;[P0476R2 \<bit> bit_cast](https://wg21.link/P0476R2) | Нет |
| &nbsp;&nbsp;[P0528R3 Атомарная инструкция сравнения и обмена с битами заполнения](https://wg21.link/P0528R3) | Нет |
| &nbsp;&nbsp;[P0591R4 Служебные функции для состава Uses-Allocator](https://wg21.link/P0591R4) | Нет |
| &nbsp;&nbsp;[P0608R3 Улучшение конструктора преобразования и назначения variant](https://wg21.link/P0608R3) | Нет |
| &nbsp;&nbsp;[P0619R4 Удаление нерекомендуемых функций C++17 в C++20](https://wg21.link/P0619R4) | Нет |
| &nbsp;&nbsp;[P0653R2 to_address()](https://wg21.link/p0653r2) | Нет |
| &nbsp;&nbsp;[P0655R1 visit\<R>()](https://wg21.link/P0655R1) | Нет |
| &nbsp;&nbsp;[P0674R1 make_shared() для массивов](https://wg21.link/p0674r1) | Нет |
| &nbsp;&nbsp;[P0718R2 atomic\<shared_ptr\<T>>, atomic\<weak_ptr\<T>>](https://wg21.link/p0718r2) | Нет |
| &nbsp;&nbsp;[P0768R1 Поддержка библиотеки для оператора сравнения "космический корабль"\<=>](https://wg21.link/p0768r1) | Нет |
| &nbsp;&nbsp;[P0811R3 midpoint(), lerp()](https://wg21.link/P0811R3) | Нет |
| &nbsp;&nbsp;[P0879R0 constexpr для функций замены](https://wg21.link/P0879R0) | Нет |
| &nbsp;&nbsp;[P0896R4 \<ranges\>](https://wg21.link/P0896R4) | Нет |
| &nbsp;&nbsp;[P0912R5 Поддержка библиотеки для сопрограмм](https://wg21.link/P0912R5) | Нет |
| &nbsp;&nbsp;[P0920R2 Поиск предварительно рассчитанных значений кэша](https://wg21.link/P0920R2) | Нет |
| &nbsp;&nbsp;[P0935R0 Удаление лишних явных конструкторов по умолчанию](https://wg21.link/P0935R0) | Нет |
| &nbsp;&nbsp;[P1001R2 execution::unseq](https://wg21.link/P1001R2) | Нет |
| &nbsp;&nbsp;[P1006R1 constexpr для pointer_traits<T*>::pointer_to()](https://wg21.link/P1006R1) | Нет |
| &nbsp;&nbsp;[P1007R3 assume_aligned()](https://wg21.link/P1007R3) | Нет |
| &nbsp;&nbsp;[P1020R1 Создание интеллектуальных указателей с инициализацией по умолчанию](https://wg21.link/P1020R1) | Нет |
| &nbsp;&nbsp;[P1023R0 constexpr для операций сравнения std::array](https://wg21.link/P1023R0) | Нет |
| &nbsp;&nbsp;[P1032R1 Прочие описатели constexpr](https://wg21.link/P1032R1) | Нет |
| &nbsp;&nbsp;[P1165R1 Согласованно распространяющиеся распределители с сохранением состояния в operator+() для basic_string](https://wg21.link/P1165R1) | Нет |
| &nbsp;&nbsp;[P1285R0 Усовершенствование требований полноты для признаков типов](https://wg21.link/P1285R0) | Нет |
| __Функции стандартной библиотеки C++17__ | __Поддерживается__ |
| &nbsp;&nbsp;[LWG 2221 Отформатированный оператор вывода для nullptr](https://cplusplus.github.io/LWG/issue2221) | VS 2019 16.1 |
| &nbsp;&nbsp;[N3911 void_t](https://wg21.link/n3911) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4089 Безопасные преобразования в unique_ptr\<T[]>](https://wg21.link/n4089) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4169 invoke()](https://wg21.link/n4169) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4190 Удаление auto_ptr, random_shuffle() и старой \<functional> Stuff](https://wg21.link/n4190) | VS 2015 <sup>[rem](#note_rem)</sup> |
| &nbsp;&nbsp;[N4258 Очистки noexcept](https://wg21.link/n4258) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4259 uncaught_exceptions()](https://wg21.link/n4259) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4277 Доступная для простого копирования функция reference_wrapper](https://wg21.link/n4277) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4279 insert_or_assign()/try_emplace() For map/unordered_map](https://wg21.link/n4279) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4280 size(), empty(), data()](https://wg21.link/n4280) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4366 Ограничение назначений unique_ptr точными значениями](https://wg21.link/n4366) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4387 Улучшение pair и tuple](https://wg21.link/n4387) | VS 2015.2 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4389 bool_constant](https://wg21.link/n4389) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4508 shared_mutex (Untimed)](https://wg21.link/n4508) | VS 2015.2 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4510 Поддержка неполных типов в vector/list/forward_list](https://wg21.link/n4510) | VS 2013 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4562 Основы работы с библиотеками: \<algorithm> sample()](https://wg21.link/n4562#alg.random.sample) | VS 2017 15.0 |
| &nbsp;&nbsp;[N4562 Основы работы с библиотеками: \<any>](https://wg21.link/n4562#any) | VS 2017 15.0 |
| &nbsp;&nbsp;[N4562 Основы работы с библиотеками: \<memory_resource>](https://wg21.link/n4562#memory.resource.synop)<br/>&nbsp;&nbsp;[P0337R0 Удаление назначения polymorphic_allocator](https://wg21.link/p0337r0) | VS 2017 15.6 |
| &nbsp;&nbsp;[N4562 Основы работы с библиотеками: \<optional>](https://wg21.link/n4562#optional) | VS 2017 15.0 |
| &nbsp;&nbsp;[N4562 Основы работы с библиотеками: \<string_view>](https://wg21.link/n4562#string.view) | VS 2017 15.0 |
| &nbsp;&nbsp;[N4562 Основы работы с библиотеками: \<tuple> apply()](https://wg21.link/n4562#tuple) | VS 2017 15.0 |
| &nbsp;&nbsp;[N4562 Library Fundamentals: алгоритм поиска Бойера-Мура search()](https://wg21.link/n4562#func.searchers.boyer_moore)<br/>&nbsp;&nbsp;[P0253R1 Исправления возвращаемых типов модуля поиска](https://wg21.link/p0253r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0003R5 Удаление динамических спецификаций исключений](https://wg21.link/p0003r5) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0004R1 Удаление нерекомендуемых псевдонимов Iostreams](https://wg21.link/p0004r1) | VS 2015.2 <sup>[rem](#note_rem)</sup> |
| &nbsp;&nbsp;[P0005R4 not_fn()](https://wg21.link/p0005r4)<br/>&nbsp;&nbsp;[P0358R1 Исправления для not_fn()](https://wg21.link/p0358r1) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0006R0 Шаблоны переменных для признаков типов (is_same_v и т. д.)](https://wg21.link/p0006r0) | VS 2015.2 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0007R1 as_const()](https://wg21.link/p0007r1) | VS 2015.2 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0013R1 Признаки типов логических операторов (conjunction и т. д.)](https://wg21.link/p0013r1) | VS 2015.2 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0024R2 Параллельные алгоритмы](https://wg21.link/p0024r2)<br/>&nbsp;&nbsp;[P0336R1 Переименование политик параллельного выполнения](https://wg21.link/p0336r1)<br/>&nbsp;&nbsp;[P0394R4 Параллельные алгоритмы следует завершить terminate() для исключений](https://wg21.link/p0394r4)<br/>&nbsp;&nbsp;[P0452R1 Объединение параллельных алгоритмов \<numeric>](https://wg21.link/p0452r1) | VS 2017 15.7 |
| &nbsp;&nbsp;[P0025R1 clamp()](https://wg21.link/p0025r1) | VS 2015.3 |
| &nbsp;&nbsp;[P0030R1 hypot(x, y, z)](https://wg21.link/p0030r1) | VS 2017 15.7 |
| &nbsp;&nbsp;[P0031R0 constexpr для \<array> (Again) и \<iterator>](https://wg21.link/p0031r0) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0032R3 Однородный интерфейса для типа variant, any или optional](https://wg21.link/p0032r3) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0033R1 Переформулировка enable_shared_from_this](https://wg21.link/p0033r1) | VS 2017 15.5 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[Расширение средств управления памяти P0040R3](https://wg21.link/p0040r3) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0063R3 Стандартная библиотека C11](https://wg21.link/p0063r3) | VS 2015 <sup>[C11](#note_C11), [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0067R5 Простые преобразования строк](https://wg21.link/p0067r5) | VS 2019 16.4<sup>[charconv](#note_charconv)</sup> |
| &nbsp;&nbsp;[P0074R0 owner_less\<>](https://wg21.link/p0074r0) | VS 2015.2 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0077R2 is_callable, is_nothrow_callable](https://wg21.link/p0077r2) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0083R3 Соединение карт и наборов](https://wg21.link/p0083r3)<br/>&nbsp;&nbsp;[P0508R0 Уточнение insert_return_type](https://wg21.link/p0508r0) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0084R2 Определение местоположения возвращаемого значения](https://wg21.link/p0084r2) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0088R3 \<variant>](https://wg21.link/p0088r3) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0092R1 \<chrono> floor(), ceil(), round(), abs()](https://wg21.link/p0092r1) | VS 2015.2 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0152R1 atomic::is_always_lock_free](https://wg21.link/p0152r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0154R1 hardware_destructive_interference_sizeи т. д.](https://wg21.link/p0154r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0156R0 lock_guard с переменным числом аргументов](https://wg21.link/p0156r0) | VS 2015.2 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0156R2 Переименование lock\_guard в scoped\_lock с переменным числом аргументов](https://wg21.link/p0156r2) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0163R0 shared_ptr::weak_type](https://wg21.link/p0163r0) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0174R2 Неподдерживаемые части библиотеки](https://wg21.link/p0174r2) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0185R1 is_swappable, is_nothrow_swappable](https://wg21.link/p0185r1) | VS 2015.3 |
| &nbsp;&nbsp;[P0209R2 make_from_tuple()](https://wg21.link/p0209r2) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0218R1 \<filesystem>](https://wg21.link/p0218r1)<br/>&nbsp;&nbsp;[P0219R1 Относительные пути для файловой системы](https://wg21.link/p0219r1)<br/>&nbsp;&nbsp;[P0317R1 Кэширование записей каталога для файловой системы](https://wg21.link/p0317r1)<br/>&nbsp;&nbsp;[P0392R0 Поддержка string_view в путях файловой системы](https://wg21.link/p0392r0)<br/>&nbsp;&nbsp;[P0430R2 Поддержка файловых систем, отличных от POSIX](https://wg21.link/p0430r2)<br/>&nbsp;&nbsp;[P0492R2 Разрешение комментариев NB для файловой системы](https://wg21.link/p0492r2) | VS 2017 15.7 <sup>[E](#note_E)</sup> |
| &nbsp;&nbsp;[P0220R1 Основы работы с библиотеками V1](https://wg21.link/p0220r1) | VS 2017 15.6 |
| &nbsp;&nbsp;[P0226R1 Специальные математические функции](https://wg21.link/p0226r1) | VS 2017 15.7 |
| &nbsp;&nbsp;[P0254R2 Интеграция string_view и std::string](https://wg21.link/p0254r2) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0258R2 has_unique_object_representations](https://wg21.link/p0258r2) | VS 2017 15.3 <sup>[G](#note_G)</sup> |
| &nbsp;&nbsp;[P0272R1 Неконстантный basic_string::data()](https://wg21.link/p0272r1) | VS 2015.3 |
| &nbsp;&nbsp;[P0295R0 gcd(), lcm()](https://wg21.link/p0295r0) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0298R3 std::byte](https://wg21.link/p0298r3) | VS 2017 15.3 <sup>[17](#note_17),&nbsp;[byte](#note_byte)</sup> |
| &nbsp;&nbsp;[P0302R1 Удаление поддержки распределителя в std::function](https://wg21.link/p0302r1) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0307R2 Повторный перевод необязательной в состояние "больше или равно"](https://wg21.link/p0307r2) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0393R3 Перевод варианта в состояние "больше или равно"](https://wg21.link/p0393r3) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0403R1 Файлы UDL для \<string_view> ("meow"sv, и т. д.)](https://wg21.link/p0403r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0414R2 shared_ptr\<T[]>, shared_ptr\<T[N]>](https://wg21.link/p0414r2)<br/>&nbsp;&nbsp;[P0497R0 Исправление shared_ptr для массивов](https://wg21.link/p0497r0) | VS 2017 15.5 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0418R2 Требования к атомарной функции compare_exchange memory_order](https://wg21.link/p0418r2) | VS 2017 15.3 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0426R1 constexpr для char_traits](https://wg21.link/p0426r1) | VS 2017 15.7 |
| &nbsp;&nbsp;[P0433R2 Интеграция вывода шаблонов для шаблонов классов в стандартной библиотеке](https://wg21.link/p0433r2)<br/>&nbsp;&nbsp;[P0739R0 Улучшение интеграции аргумента шаблона класса со стандартной библиотекой](https://wg21.link/p0739r0) | VS 2017 15.7 |
| &nbsp;&nbsp;[P0435R1 Переработка common_type](https://wg21.link/p0435r1)<br/>&nbsp;&nbsp;[P0548R1 Настройка common\_type и длительности](https://wg21.link/p0548r1) | VS 2017 15.3 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0504R0 Пересмотр in_place_t/in_place_type_t\<T>/in_place_index_t\<I>](https://wg21.link/p0504r0) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0505R0 constexpr для \<chrono> (Again)](https://wg21.link/p0505r0) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0510R0 Отклонение вариантов Nothing, Arrays, References и Incomplete Type](https://wg21.link/p0510r0) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0513R0 Подделка хэша](https://wg21.link/p0513r0)<br/>&nbsp;&nbsp;[P0599R1 Хэш noexcept](https://wg21.link/p0599r1) | VS 2017 15.3 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0516R0 Пометка копирования shared_future как noexcept](https://wg21.link/p0516r0) | VS 2017 15.3 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0517R0 Создание future_error из future_errc](https://wg21.link/p0517r0) | VS 2017 15.3 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0521R0 Неподдерживаемая shared_ptr::unique()](https://wg21.link/p0521r0) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0558R1 Разрешение несоответствий базового класса с именем atomic\<T>](https://wg21.link/p0558r1) | VS 2017 15.3 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0595R2 std::is_constant_evaluated()](https://wg21.link/P0595R2) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0602R4 Распространение тривиальности копирования и перемещения в variant/optional](https://wg21.link/P0602R4) | VS 2017 15.3<sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0604R0 Изменение is\_callable/result\_of на invoke\_result, is\_invocable, is\_nothrow\_invocable](https://wg21.link/p0604r0) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0607R0 Встроенные переменные для стандартной библиотеки](https://wg21.link/p0607r0) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0618R0 Перевод \<codecvt> в разряд нерекомендуемых](https://wg21.link/p0618r0) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0682R1 Исправление простых преобразований строк](https://wg21.link/P0682R1) | VS 2015 15.7 <sup>[17](#note_17)</sup> |
| __Функции стандартной библиотеки C++14__ | __Поддерживается__ |
| &nbsp;&nbsp;[N3462 SFINAE result_of](https://wg21.link/n3462) | VS 2015.2 |
| &nbsp;&nbsp;[N3302 constexpr для \<complex>](https://wg21.link/n3302) | VS 2015 |
| &nbsp;&nbsp;[N3469 constexpr для \<chrono>](https://wg21.link/n3469) | VS 2015 |
| &nbsp;&nbsp;[N3470 constexpr для \<array>](https://wg21.link/n3470) | VS 2015 |
| &nbsp;&nbsp;[N3471 constexpr для \<initializer_list>, \<tuple>, \<utility>](https://wg21.link/n3471) | VS 2015 |
| &nbsp;&nbsp;[N3545 integral_constant::operator()()](https://wg21.link/n3545) | VS 2015 |
| &nbsp;&nbsp;[N3642 Файлы UDL для \<chrono>, \<string> (1729ms, "meow"s, и т. д.)](https://wg21.link/n3642) | VS 2015 |
| &nbsp;&nbsp;[N3644 Пустые однонаправленные итераторы](https://wg21.link/n3644) | VS 2015 |
| &nbsp;&nbsp;[N3654 quoted()](https://wg21.link/n3654) | VS 2015 |
| &nbsp;&nbsp;[N3657 Разнородный ассоциативный поиск](https://wg21.link/n3657) | VS 2015 |
| &nbsp;&nbsp;[N3658 integer_sequence](https://wg21.link/n3658) | VS 2015 |
| &nbsp;&nbsp;[N3659 shared_mutex (Timed)](https://wg21.link/n3659) | VS 2015 |
| &nbsp;&nbsp;[N3668 exchange()](https://wg21.link/n3668) | VS 2015 |
| &nbsp;&nbsp;[N3669 Исправление функций-членов constexpr без константы](https://wg21.link/n3669) | VS 2015 |
| &nbsp;&nbsp;[N3670 get\<T>()](https://wg21.link/n3670) | VS 2015 |
| &nbsp;&nbsp;[N3671 equal(), is_permutation(), mismatch() с двойным диапазоном](https://wg21.link/n3671) | VS 2015 |
| &nbsp;&nbsp;[N3778 Освобождение с указанием размера](https://wg21.link/n3778) | VS 2015 |
| &nbsp;&nbsp;[N3779 Файлы UDL \<complex> (3.14i и т. д.)](https://wg21.link/n3779) | VS 2015 |
| &nbsp;&nbsp;[N3789 constexpr для \<functional>](https://wg21.link/n3789) | VS 2015 |
| &nbsp;&nbsp;[N3887 tuple_element_t](https://wg21.link/n3887) | VS 2015 |
| &nbsp;&nbsp;[N3891 Переименование shared_mutex (Timed) в shared_timed_mutex](https://wg21.link/n3891) | VS 2015 |
| &nbsp;&nbsp;[N3346 Требования к минимальным элементам контейнера](https://wg21.link/n3346) | VS 2013 |
| &nbsp;&nbsp;[N3421 Прозрачные функции операторов (less\<> и т. д.)](https://wg21.link/n3421) | VS 2013 |
| &nbsp;&nbsp;[N3655 Шаблоны псевдонимов для \<type_traits> (decay_t и т. д.)](https://wg21.link/n3655) | VS 2013 |
| &nbsp;&nbsp;[N3656 make_unique()](https://wg21.link/n3656) | VS 2013 |

Набор совместно указанных документов указывает на стандартную функцию с одним или несколькими утвержденными улучшениями или расширениями. Эти функции реализованы вместе.

### <a name="supported-values"></a>Поддерживаемые значения

__Нет__ означает, что функция еще не реализована.\
__Частично__ указывает на частичную реализацию. Дополнительные сведения см. в разделе "Примечания".\
__VS 2010__ — функции, которые поддерживаются в Visual Studio 2010.\
__VS 2013__ — функции, которые поддерживаются в Visual Studio 2013.\
__VS 2015__ — функции, которые поддерживаются в Visual Studio 2015 (RTW).\
__VS 2015.2__ и __VS 2015.3__ — функции, которые поддерживаются в Visual Studio 2015 с обновлением 2 и Visual Studio 2015 с обновлением 3, соответственно.\
__VS 2017 15.0__ — функции, которые поддерживаются в Visual Studio 2017 версии 15.0 (RTW).\
__VS 2017 15.3__ — функции, которые поддерживаются в Visual Studio 2017 версии 15.3.\
__VS 2017 15.5__ — функции, которые поддерживаются в Visual Studio 2017 версии 15.5.\
__VS 2017 15.7__ — функции, которые поддерживаются в Visual Studio 2017 версии 15.7.\
__VS 2019 16.0__ — функции, которые поддерживаются в Visual Studio 2019 версии 16.0 (RTW).\
__VS 2019 16.1__ — функции, которые поддерживаются в Visual Studio 2019 версии 16.1.\
__VS 2019 16.2__ — функции, которые поддерживаются в Visual Studio 2019 версии 16.2.\
__VS 2019 16.3__ — функции, которые поддерживаются в Visual Studio 2019 версии 16.3.\
__VS 2019 16.4__ — функции, которые поддерживаются в Visual Studio 2019 версии 16.4.\
__VS 2019 16.5__ — функции, которые поддерживаются в Visual Studio 2019 версии 16.5.

### <a name="notes"></a>Примечания

<a name="note_A"></a>__A__ В режиме [/std:c++14](../build/reference/std-specify-language-standard-version.md) спецификации динамических исключений остаются нереализованными и `throw()` по-прежнему рассматривается как синоним `__declspec(nothrow)`. В C++17 спецификации динамических исключений в основном удалены в P0003R5, за исключением одного vestige: `throw()`, который является устаревшим и должен вести себя как синоним `noexcept`. В режиме [/std:c++17](../build/reference/std-specify-language-standard-version.md) параметры MSVC теперь соответствуют стандарту, обеспечивая `throw()` то же поведение, что и `noexcept`, т. е. через завершение.

Параметр компилятора [/Zc:noexceptTypes](../build/reference/zc-noexcepttypes.md) требует старого поведения `__declspec(nothrow)`. Вполне вероятно, что `throw()` будет удален в C++20. Для того чтобы помочь с приведением кода в соответствие с указанными изменениями в стандарте и нашей реализации, для параметров [/std:c++17](../build/reference/std-specify-language-standard-version.md) и [/permissive-](../build/reference/permissive-standards-conformance.md) были добавлены новые предупреждения компилятора для исключений, связанных с несоответствием спецификациям.

<a name="note_B"></a>__B__ Поддерживается в режиме [/permissive-](../build/reference/permissive-standards-conformance.md) в Visual Studio 2017 версии 15.7. Подробные сведения см. в записи блога [Two-phase name lookup support comes to MSVC](https://devblogs.microsoft.com/cppblog/two-phase-name-lookup-support-comes-to-msvc/) (В MSVC будет добавлена поддержка двухэтапного поиска имени).

<a name="note_C"></a>__C__ Поддержка компилятора для правил препроцессора C99 является неполной в Visual Studio 2017. Мы переделываем препроцессор и начали поставлять эти изменения в Visual Studio 2017 версии 15.8 с параметром [/experimental:preprocessor](../build/reference/experimental-preprocessor.md) компилятора.

<a name="note_D"></a>__D__ поддерживается в [/std: c++14](../build/reference/std-specify-language-standard-version.md) с отключаемым предупреждением [C4984](../error-messages/compiler-warnings/compiler-warning-c4984.md).

<a name="note_E"></a>__E__ Это совершенно новая, несовместимая с предыдущей версией `std::experimental` реализация, необходимость в которой вызвана добавлением поддержки символьных ссылок, исправлением ошибок и изменениями в поведении, которое требуется для соблюдения стандарта. В настоящее время включение \<filesystem> предоставляет новую функцию `std::filesystem` и предыдущую функцию `std::experimental::filesystem`, а включение \<experimental/filesystem> предоставляет только старую экспериментальную реализацию. Экспериментальная реализация будет УДАЛЕНА в следующем выпуске библиотек, содержащем изменения в ABI.

<a name="note_G"></a>__G__ Поддерживается встроенными функциями компилятора.

<a name="note_14"></a>__14__ Эти функции C++17/20 всегда включены, даже если указано значение по умолчанию [/std:c++14](../build/reference/std-specify-language-standard-version.md). Это происходит, потому что функция реализована до введения параметров **/std** или из-за сложных условий реализации.

<a name="note_17"></a>__17__ Эти функции выключены параметром компилятора [/std:c++17](../build/reference/std-specify-language-standard-version.md) (или [/std:c++latest](../build/reference/std-specify-language-standard-version.md)).

<a name="note_20"></a>__20__ Эти функции включены параметром компилятора [/std:c++latest](../build/reference/std-specify-language-standard-version.md). После завершения реализации C++20 будет добавлен новый параметр компилятора **/std:c++20**, с которым эти функции также будут доступны.

<a name="note_byte"></a>__byte__ `std::byte` поддерживают [/std:c++17](../build/reference/std-specify-language-standard-version.md) (или [/std:c++latest](../build/reference/std-specify-language-standard-version.md)), но так как в некоторых случаях эта версия может конфликтовать с заголовками Windows SDK, предусмотрен детально настроенный макрос явного отказа. Его можно отключить, определив `_HAS_STD_BYTE` как `0`.

<a name="note_C11"></a>__C11__ В Universal CRT реализованы части стандартной библиотеки C11, необходимые для C++17, за исключением альтернативных спецификаторов преобразования E и O C99 `strftime()`, исключительного режима C11 `fopen()` и C11 `aligned_alloc()`. Маловероятно, что последний компонент будет реализован, так как в C11 `aligned_alloc()` указан так, что он становится несовместимым с реализацией `free()`, а именно, `free()` должен быть способен обрабатывать точно выровненные распределения.

<a name="note_rem"></a>__rem__ Компоненты удалены, когда был указан параметр компилятора [/std:c++17](../build/reference/std-specify-language-standard-version.md) (или [/std:c++latest](../build/reference/std-specify-language-standard-version.md)). Эти функции можно будет снова включить для упрощения перехода к новым языковым режимам с помощью таких макросов: `_HAS_AUTO_PTR_ETC`, `_HAS_FUNCTION_ALLOCATOR_SUPPORT`, `_HAS_OLD_IOSTREAMS_MEMBERS` и `_HAS_UNEXPECTED`.

<a name="note_charconv"></a>__charconv__ `from_chars()` и `to_chars()` доступны для целых чисел. Хронологический порядок реализации `from_chars()` с плавающей запятой и `to_chars()` с плавающей запятой выглядит следующим образом:
- VS 2017 15.7: `from_chars()` и `to_chars()` для целых чисел.
- VS 2017 15.8: `from_chars()` с плавающей запятой.
- VS 2017 15.9: `to_chars()` с плавающей запятой переопределяет число с наименьшим числом десятичных знаков.
- VS 2019 16.0: `to_chars()` с плавающей запятой переопределяет шестнадцатеричное число с наименьшим числом знаков и точное шестнадцатеричное число.
- VS 2019 16.2: `to_chars()` с плавающей запятой переопределяет точные фиксированные значения и точные значения научных вычислений.
- VS 2019 16.4: `to_chars()` с плавающей запятой переопределяет общие точные значения.

<a name ="note_parallel"></a>__parallel__ Разработка библиотек для параллельных алгоритмов C++17 завершена. Это не значит, что каждый алгоритм работает параллельно в каждом случае. Параллелизуются наиболее важные алгоритмы, однако сигнатуры политик выполнения предоставляются даже тогда, когда алгоритмы не удалось распараллелить. В нашей реализации центральный внутренний заголовок yvals_core.h содержит следующие "Заметки о параллельных алгоритмах": C++ позволяет реализовать параллельные алгоритмы как вызовы серийных алгоритмов. Эта реализация распараллеливает некоторые распространенные вызовы алгоритмов, но не все.

Параллельно работают следующие алгоритмы:

- `adjacent_difference`, `adjacent_find`, `all_of`, `any_of`, `count`, `count_if`, `equal`, `exclusive_scan`, `find`, `find_end`, `find_first_of`, `find_if`, `find_if_not`, `for_each`, `for_each_n`, `inclusive_scan`, `is_heap`, `is_heap_until`, `is_partitioned`, `is_sorted`, `is_sorted_until`, `mismatch`, `none_of`, `partition`, `reduce`, `remove`, `remove_if`, `replace`, `replace_if`, `search`, `search_n`, `set_difference`, `set_intersection`, `sort`, `stable_sort`, `transform`, `transform_exclusive_scan`, `transform_inclusive_scan`, `transform_reduce`

Следующие алгоритмы в настоящее время еще не распараллелены:

- Нет заметного увеличения производительности от параллелизма на целевом оборудовании. Все алгоритмы, которые просто копируют или переставляют элементы без создания ветвей, обычно ограничены пропускной способностью памяти:
  - `copy`, `copy_n`, `fill`, `fill_n`, `move`, `reverse`, `reverse_copy`, `rotate`, `rotate_copy`, `shift_left`, `shift_right`, `swap_ranges`
- Существует путаница относительно требований пользователей к параллелизму, по-видимому, как и в категории выше:
  - `generate`, `generate_n`
- Вероятно, эффективный параллелизм недостижим:
  - `partial_sort`, `partial_sort_copy`
- Оценка пока недоступна. Параллелизм может быть реализован в будущих выпусках, и предполагается, что он улучшит производительность:
  - `copy_if`, `includes`, `inplace_merge`, `lexicographical_compare`, `max_element`, `merge`, `min_element`, `minmax_element`, `nth_element`, `partition_copy`, `remove_copy`, `remove_copy_if`, `replace_copy`, `replace_copy_if`, `set_symmetric_difference`, `set_union`, `stable_partition`, `unique`, `unique_copy`

## <a name="see-also"></a>См. также

[Справочник по языку C++](../cpp/cpp-language-reference.md)\
[Стандартная библиотека C++](../standard-library/cpp-standard-library-reference.md)\
[Улучшения соответствия C++ в Visual Studio](cpp-conformance-improvements.md)\
[Новые возможности C++ в Visual Studio](what-s-new-for-visual-cpp-in-visual-studio.md)\
[Журнал изменений Visual C++ 2003–2015](../porting/visual-cpp-change-history-2003-2015.md)\
[Новые возможности Visual C++ 2003–2015](../porting/visual-cpp-what-s-new-2003-through-2015.md)\
[Блог группы разработчиков C++](https://devblogs.microsoft.com/cppblog/)
