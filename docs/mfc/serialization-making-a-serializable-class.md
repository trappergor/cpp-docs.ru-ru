---
title: 'Сериализация: Создание сериализуемого класса | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4412e8db861ac522c0f1b1d7192bfbb83612d64c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="serialization-making-a-serializable-class"></a>Сериализация. Создание сериализуемого класса
Пять основных шагов необходимы, чтобы сделать класс сериализуемым. Они перечислены ниже и описаны в следующих разделах:  
  
1.  [Класса, производного от CObject](#_core_deriving_your_class_from_cobject) (или некоторого класса, производного от `CObject`).  
  
2.  [Переопределение функции-члена сериализации](#_core_overriding_the_serialize_member_function).  
  
3.  [С помощью DECLARE_SERIAL-макрос](#_core_using_the_declare_serial_macro) в объявлении класса.  
  
4.  [Определение конструктора без аргументов](#_core_defining_a_constructor_with_no_arguments).  
  
5.  [С помощью IMPLEMENT_SERIAL-макрос в файле реализации](#_core_using_the_implement_serial_macro_in_the_implementation_file) для своего класса.  
  
 При вызове метода `Serialize` напрямую, а не через >> и << операторы [CArchive](../mfc/reference/carchive-class.md), последние три действия не требуются для сериализации.  
  
##  <a name="_core_deriving_your_class_from_cobject"></a> Класса, производного от CObject  
 Базовая сериализация протокола и функциональные возможности определены в `CObject` класса. Путем наследования класса из `CObject` (или из класса, производного от `CObject`), как показано в следующем объявлении класса `CPerson`, можно получить доступ к сериализации протокола и функциональность `CObject`.  
  
##  <a name="_core_overriding_the_serialize_member_function"></a> Переопределение сериализации функции-члена  
 `Serialize` Функции-члена, который определен в `CObject` класс, ответственный за фактически сериализации данных, необходимые для отслеживания текущего состояния объекта. `Serialize` Функция имеет `CArchive` аргумент, который используется для чтения и записи данных объекта. [CArchive](../mfc/reference/carchive-class.md) объект имеет функцию-член, `IsStoring`, которое указывает ли `Serialize` хранения (записи данных) или загрузке (чтение данных). Использование результатов `IsStoring` как, либо вставке данных объекта в `CArchive` объекта с помощью оператора вставки (**<\<**) или извлечения данных с помощью оператора извлечения ( **>>**).  
  
 Рассмотрим класс, производный от `CObject` и имеет две новые переменные-члены, типов `CString` и **WORD**. В следующем фрагменте объявление класса показан новый член переменных и объявление переопределенного `Serialize` функции-члена:  
  
 [!code-cpp[NVC_MFCSerialization#1](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_1.h)]  
  
#### <a name="to-override-the-serialize-member-function"></a>Чтобы переопределить функцию-член сериализации  
  
1.  Вызов базового класса версии `Serialize` чтобы убедиться в том, что сериализуется наследуемые часть объекта.  
  
2.  Вставить или извлечь переменные-члены, относящиеся к классу.  
  
     Операторы вставки и извлечения взаимодействия с классом архив для чтения и записи данных. Следующий пример показывает, как реализовать `Serialize` для `CPerson` класса, объявленные выше:  
  
     [!code-cpp[NVC_MFCSerialization#2](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_2.cpp)]  
  
 Можно также использовать [CArchive::Read](../mfc/reference/carchive-class.md#read) и [CArchive::Write](../mfc/reference/carchive-class.md#write) функции-члены для чтения и записи больших объемов нетипизированных данных.  
  
##  <a name="_core_using_the_declare_serial_macro"></a> С помощью DECLARE_SERIAL-макрос  
 `DECLARE_SERIAL` Макрос является обязательным в объявления классов, которые будут поддерживать сериализацию, как показано ниже:  
  
 [!code-cpp[NVC_MFCSerialization#3](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_3.h)]  
  
##  <a name="_core_defining_a_constructor_with_no_arguments"></a> Определение конструктора без аргументов  
 MFC требуется конструктор по умолчанию, при повторном создании объектов при их десериализации (загружен с диска). В процессе десериализации заполнит все переменные-члены значения, необходимые для повторного создания объекта.  
  
 Этот конструктор может быть объявлен как открытый, защищенный или закрытый. Если вы вносите защищенным, либо закрытым, поможет убедитесь в том, что он будет использоваться только функциями сериализации. Конструктор должен поместить объект в состоянии, которое позволяет удалить при необходимости.  
  
> [!NOTE]
>  Если вы забудете определение конструктора без аргументов в класс, который использует `DECLARE_SERIAL` и `IMPLEMENT_SERIAL` макросы, вы получите предупреждение компилятора «нет конструктора по умолчанию» в строке где `IMPLEMENT_SERIAL` используется макрос.  
  
##  <a name="_core_using_the_implement_serial_macro_in_the_implementation_file"></a> Использование в файле реализации IMPLEMENT_SERIAL-макрос  
 `IMPLEMENT_SERIAL` Макрос используется для определения различных функций, необходимых при наследовании из сериализуемого класса `CObject`. Используйте этот макрос в файле реализации (. CPP) для своего класса. Первые два аргумента в макрос — это имя класса и имя его непосредственно к базовому классу.  
  
 Третий аргумент этот макрос является номером схемы. Число схемы — по существу номер версии для объектов класса. Используйте целое число больше или равно 0 для некоторых схем. (Не путайте этот номер схемы с терминологии связанных баз данных).  
  
 Код сериализации MFC проверяет номер схемы при чтении объектов в памяти. Если номер схемы объекта на диске не соответствует количество схемы классов в памяти, вызывает исключение библиотеки `CArchiveException`, предотвращая программы чтения неправильная версия объекта.  
  
 Если требуется вашей `Serialize` функции-члена для считывания нескольких версий — то есть файлы с разными версиями приложения, можно использовать значение **VERSIONABLE_SCHEMA** как аргумент `IMPLEMENT_SERIAL` макрос. Сведения об использовании и пример см. в разделе `GetObjectSchema` функции-члена класса `CArchive`.  
  
 В следующем примере показано, как использовать `IMPLEMENT_SERIAL` для класса `CPerson`, производный от `CObject`:  
  
 [!code-cpp[NVC_MFCSerialization#4](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_4.cpp)]  
  
 При наличии сериализуемого класса можно сериализовать объекты класса, как описано в статье [сериализации: сериализация объекта](../mfc/serialization-serializing-an-object.md).  
  
## <a name="see-also"></a>См. также  
 [Сериализация](../mfc/serialization-in-mfc.md)

