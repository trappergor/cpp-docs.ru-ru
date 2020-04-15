---
title: Сериализация. Создание сериализуемого класса
ms.date: 11/04/2016
helpviewer_keywords:
- serializable class [MFC]
- DECLARE_SERIAL macro [MFC]
- default constructor [MFC]
- VERSIONABLE_SCHEMA macro [MFC]
- classes [MFC], derived
- IMPLEMENT_SERIAL macro [MFC]
- no-arguments constructor [MFC]
- Serialize method, overriding
- defaults [MFC], constructor
- CObject class [MFC], deriving serializable classes
- constructors [MFC], defining with no arguments
- serialization [MFC], serializable classes
- no default constructor
ms.assetid: 59a14d32-1cc8-4275-9829-99639beee27c
ms.openlocfilehash: 9648bd4f516a5f174534336b1ca3b42bb51ca0c4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372707"
---
# <a name="serialization-making-a-serializable-class"></a>Сериализация. Создание сериализуемого класса

Для того чтобы сделать класс сериализируемым, требуется пять основных шагов. Они перечислены ниже и объяснены в следующих разделах:

1. [Вывод вашего класса из CObject](#_core_deriving_your_class_from_cobject) (или из `CObject`какого-либо класса, полученного из).

1. [Переопределение функции участника Serialize.](#_core_overriding_the_serialize_member_function)

1. [Использование DECLARE_SERIAL макроса](#_core_using_the_declare_serial_macro) в декларации класса.

1. [Определение конструктора, который не принимает никаких аргументов.](#_core_defining_a_constructor_with_no_arguments)

1. [Использование IMPLEMENT_SERIAL макроса в файле реализации](#_core_using_the_implement_serial_macro_in_the_implementation_file) для вашего класса.

Если вы `Serialize` звоните напрямую, а не через >> и << операторы [CArchive,](../mfc/reference/carchive-class.md)то для сериализации не требуется последние три шага.

## <a name="deriving-your-class-from-cobject"></a><a name="_core_deriving_your_class_from_cobject"></a>Производство вашего класса от CObject

Базовый протокол и функциональность сериализации `CObject` определены в классе. Выводя свой класс `CObject` из (или из класса, полученного из), `CObject`как `CPerson`показано в следующей декларации класса, `CObject`вы получаете доступ к протоколу сериализации и функциональности .

## <a name="overriding-the-serialize-member-function"></a><a name="_core_overriding_the_serialize_member_function"></a>Переопределение функции участника Serialize

Функция `Serialize` члена, определяемая в `CObject` классе, отвечает за фактическое сериализацию данных, необходимых для захвата текущего состояния объекта. Функция `Serialize` имеет `CArchive` аргумент, который она использует для чтения и записи данных объекта. Объект [CArchive](../mfc/reference/carchive-class.md) имеет функцию `IsStoring`члена, `Serialize` которая указывает, является ли хранение (письменные данные) или загрузка (данные чтения). Используя результаты `IsStoring` в качестве руководства, вы либо вставляете данные объекта в `CArchive` объект с оператором вставки ()**<** или извлекаете данные с оператором экстракции ().**>>**

Рассмотрим класс, который `CObject` является производным от и `CString` имеет две новые переменные члена, типов и **WORD**. Следующий фрагмент объявления класса показывает новые переменные члена `Serialize` и декларацию для перевереванной функции члена:

[!code-cpp[NVC_MFCSerialization#1](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_1.h)]

#### <a name="to-override-the-serialize-member-function"></a>Переопределение функции участника Serialize

1. Позвоните в версию базового `Serialize` класса, чтобы убедиться, что унаследованная часть объекта сериализована.

1. Вставьте или извлеките переменные участника, характерные для вашего класса.

   Операторы вставки и извлечения взаимодействуют с классом архива для чтения и записи данных. В следующем примере `Serialize` показано, `CPerson` как реализовать для класса, объявленного выше:

   [!code-cpp[NVC_MFCSerialization#2](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_2.cpp)]

Вы также можете использовать [CArchive::Read](../mfc/reference/carchive-class.md#read) и [CArchive::Write](../mfc/reference/carchive-class.md#write) функции участника для чтения и записи больших объемов нетиповых данных.

## <a name="using-the-declare_serial-macro"></a><a name="_core_using_the_declare_serial_macro"></a>Использование DECLARE_SERIAL Макро

В декларации классов требуется DECLARE_SERIAL макрос, который будет поддерживать сериализацию, как показано здесь:

[!code-cpp[NVC_MFCSerialization#3](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_3.h)]

## <a name="defining-a-constructor-with-no-arguments"></a><a name="_core_defining_a_constructor_with_no_arguments"></a>Определение конструктора без аргументов

MFC требует конструктора по умолчанию, когда он воссоздает ваши объекты по мере их десериализации (загружены с диска). Процесс десериализации заполняет все переменные членов значениями, необходимыми для воссоздания объекта.

Этот конструктор может быть объявлен публичным, защищенным или частным. Если вы сделаете его защищенным или закрытым, вы поможете убедиться, что он будет использоваться только функциями сериализации. Конструктор должен поместить объект в состояние, которое позволяет его удалить в случае необходимости.

> [!NOTE]
> Если вы забыли определить конструктор без аргументов в классе, который использует DECLARE_SERIAL и IMPLEMENT_SERIAL макросов, вы получите предупреждение компилятора "нет конструктора по умолчанию" на линии, где используется IMPLEMENT_SERIAL макрос.

## <a name="using-the-implement_serial-macro-in-the-implementation-file"></a><a name="_core_using_the_implement_serial_macro_in_the_implementation_file"></a>Использование IMPLEMENT_SERIAL Макро в файле реализации

Макрос IMPLEMENT_SERIAL используется для определения различных функций, необходимых `CObject`при извлечении серийного класса из. Этот макрос используется в файле реализации (. CPP) для вашего класса. Первыми двумя аргументами макроса являются название класса и название его непосредственного базового класса.

Третьим аргументом для этого макроса является число схем. Номер схемы по существу является номером версии для объектов класса. Используйте целый ряд, превышающей или равный 0, для числа схем. (Не путайте этот номер схемы с терминологией базы данных.)

Код сериализации MFC проверяет номер схемы при чтении объектов в памяти. Если номер схемы объекта на диске не совпадает с номером схемы класса в `CArchiveException`памяти, библиотека будет бросать, предотвращая чтение программы неправильной версией объекта.

Если вы `Serialize` хотите, чтобы функция участника могла читать несколько версий, т.е. файлы, написанные с различными версиями приложения, вы можете использовать *значение VERSIONABLE_SCHEMA* в качестве аргумента для IMPLEMENT_SERIAL макроса. Для информации об использовании `GetObjectSchema` и примере см. функцию участника класса. `CArchive`

Следующий пример показывает, как использовать `CPerson`IMPLEMENT_SERIAL для класса, `CObject`то есть происходит от:

[!code-cpp[NVC_MFCSerialization#4](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_4.cpp)]

Если у вас есть серийный класс, вы можете сериализовать объекты класса, как обэтом этом говорится в статье [Serialization: Serializing an Object.](../mfc/serialization-serializing-an-object.md)

## <a name="see-also"></a>См. также раздел

[Сериализация](../mfc/serialization-in-mfc.md)
