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
ms.openlocfilehash: 995744381c8f82dc637e4aa0452e37af170b168b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62308106"
---
# <a name="serialization-making-a-serializable-class"></a>Сериализация. Создание сериализуемого класса

Пять основных шагов необходимы, чтобы сделать класс сериализуемым. Они перечислены ниже и описано в следующих разделах:

1. [Класса, производного от CObject](#_core_deriving_your_class_from_cobject) (или некоторого класса, производного от `CObject`).

1. [Переопределение функцию-член Serialize](#_core_overriding_the_serialize_member_function).

1. [С помощью declare_serial-макрос](#_core_using_the_declare_serial_macro) в объявлении класса.

1. [Определение конструктора без аргументов](#_core_defining_a_constructor_with_no_arguments).

1. [С помощью IMPLEMENT_SERIAL-макрос в файле реализации](#_core_using_the_implement_serial_macro_in_the_implementation_file) для класса.

При вызове метода `Serialize` напрямую, а не через >> и << операторы [CArchive](../mfc/reference/carchive-class.md), последние три действия не требуются для сериализации.

##  <a name="_core_deriving_your_class_from_cobject"></a> Класса, производного от CObject

Базовая сериализация протокола и функциональные возможности определяются в `CObject` класса. Путем наследования от класса `CObject` (или из класса, производного от `CObject`), как показано в следующем объявлении класса `CPerson`, вы получаете доступ к сериализации протокола и функциональных возможностей `CObject`.

##  <a name="_core_overriding_the_serialize_member_function"></a> Переопределение сериализации функция-член

`Serialize` Функция-член, который определен в `CObject` класса, отвечает за фактически сериализации данными, необходимыми для записи текущего состояния объекта. `Serialize` Функция имеет `CArchive` аргумент, который используется для чтения и записи данных объекта. [CArchive](../mfc/reference/carchive-class.md) объект имеет функцию-член, `IsStoring`, которое указывает ли `Serialize` хранения (запись данных) или загрузке (чтение данных). Использование результатов `IsStoring` как руководство, вы либо вставки объекта данных в `CArchive` объекта с помощью оператора вставки (**<\<**) или извлечение данных с помощью оператора извлечения ( **>>**).

Рассмотрим класс, производный от `CObject` и имеет две новые переменные-члены, типов `CString` и **WORD**. В следующем фрагменте объявление класса показан новый член переменных и объявление переопределенного `Serialize` функция-член:

[!code-cpp[NVC_MFCSerialization#1](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_1.h)]

#### <a name="to-override-the-serialize-member-function"></a>Чтобы переопределить функцию-член Serialize

1. Вызовите вашей версии базового класса `Serialize` чтобы убедиться в том, что сериализуется унаследованные часть объекта.

1. Вставить или извлечь переменные-члены, относящиеся к классу.

   Операторы вставки и извлечения взаимодействия с классом архив для чтения и записи данных. В следующем примере показано, как реализовать `Serialize` для `CPerson` класс, объявленный над:

   [!code-cpp[NVC_MFCSerialization#2](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_2.cpp)]

Можно также использовать [CArchive::Read](../mfc/reference/carchive-class.md#read) и [CArchive::Write](../mfc/reference/carchive-class.md#write) функции-члены для чтения и записи больших объемов нетипизированных данных.

##  <a name="_core_using_the_declare_serial_macro"></a> С помощью declare_serial-макрос

Declare_serial-макрос требуется в объявления классов, которые будут поддерживать сериализацию, как показано ниже:

[!code-cpp[NVC_MFCSerialization#3](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_3.h)]

##  <a name="_core_defining_a_constructor_with_no_arguments"></a> Определение конструктора без аргументов

MFC требуется конструктор по умолчанию, при повторном создании объектов при их десериализации (загружен с диска). В процессе десериализации заполнит все переменные-члены значения, необходимые для повторного создания объекта.

Этот конструктор может быть объявлен как открытый, защищенный или закрытый. Если сделать его защищенный или закрытый, позволяет убедиться, что он будет использоваться только функциями сериализации. Конструктор должен поместить объект в состоянии, допускающем оно будет удалено при необходимости.

> [!NOTE]
>  Если вы забыли определение конструктора без аргументов в классе, который использует макросы DECLARE_SERIAL и IMPLEMENT_SERIAL, вы получите предупреждение компилятора «нет конструктора по умолчанию» в строке, где используется IMPLEMENT_SERIAL-макрос.

##  <a name="_core_using_the_implement_serial_macro_in_the_implementation_file"></a> В файле реализации IMPLEMENT_SERIAL-макрос

IMPLEMENT_SERIAL-макрос используется для определения различных функций, необходимых при наследовании из сериализуемого класса `CObject`. Используйте этот макрос в файле реализации (. CPP) для класса. Первые два аргумента в макрос: имя класса и имя его непосредственный базовый класс.

Этот макрос третий аргумент является числом схемы. Номер схемы — по сути это номер версии для объектов данного класса. Используйте целое число больше или равно 0 для номера схемы. (Не путайте этот номер схемы с терминологии связанных баз данных).

Код сериализации MFC проверяет номер схемы при чтении объектов в памяти. Если номер схемы объекта, на диске не соответствует номер схемы класса в памяти, библиотека выдаст `CArchiveException`, предотвращая программы чтения используется неверная версия файла объекта.

Если вы хотите, чтобы ваши `Serialize` функция-член, чтобы иметь возможность чтения нескольких версий — то есть файлы, записанные с разными версиями приложения, можно использовать значение *VERSIONABLE_SCHEMA* как аргумент IMPLEMENT_SERIAL макрос. Сведения об использовании и примеры см. в разделе `GetObjectSchema` функция-член класса `CArchive`.

В следующем примере показано, как использовать IMPLEMENT_SERIAL для класса, `CPerson`, то есть производным от `CObject`:

[!code-cpp[NVC_MFCSerialization#4](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_4.cpp)]

При наличии сериализуемого класса можно сериализовать объекты класса, как описано в статье [сериализации: Сериализация объекта](../mfc/serialization-serializing-an-object.md).

## <a name="see-also"></a>См. также

[Сериализация](../mfc/serialization-in-mfc.md)
