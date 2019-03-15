---
title: Импорт с помощью DEF-файлов
ms.date: 11/04/2016
helpviewer_keywords:
- importing DLLs [C++], DEF files
- def files [C++], importing with
- .def files [C++], importing with
- dllimport attribute [C++], DEF files
- DLLs [C++], DEF files
ms.assetid: aefdbf50-f603-488a-b0d7-ed737bae311d
ms.openlocfilehash: 13a6a375d6200f73dd9845d057d1954c2b65485c
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57815337"
---
# <a name="importing-using-def-files"></a>Импорт с помощью DEF-файлов

Если вы решили использовать **__declspec(dllimport)** наряду с DEF-файла, следует изменить в DEF-файле и использовать данные вместо КОНСТАНТЫ для уменьшения вероятности того, что неверный код вызовет ошибку:

```
// project.def
LIBRARY project
EXPORTS
   ulDataInDll   DATA
```

В следующей таблице показаны почему.

|Ключевое слово|Выдает в библиотеке импорта|Экспорты|
|-------------|---------------------------------|-------------|
|`CONSTANT`|`_imp_ulDataInDll`, `_ulDataInDll`|`_ulDataInDll`|
|`DATA`|`_imp_ulDataInDll`|`_ulDataInDll`|

С помощью **__declspec(dllimport)** и КОНСТАНТЫ перечислены оба `imp` версии и внешнее имя в LIB-файле библиотеки DLL импортировать библиотеку, которая создается для явного связывания. С помощью **__declspec(dllimport)** и списки данных просто `imp` версия имени.

Если вы используете КОНСТАНТА, одно из следующих конструкций кода может использоваться для доступа к `ulDataInDll`:

```
__declspec(dllimport) ULONG ulDataInDll; /*prototype*/
if (ulDataInDll == 0L)   /*sample code fragment*/
```

\-или-

```
ULONG *ulDataInDll;      /*prototype*/
if (*ulDataInDll == 0L)  /*sample code fragment*/
```

Тем не менее, если вы используете данные в DEF-файле, только код, скомпилированный со следующим определением могут обращаться к переменной `ulDataInDll`:

```
__declspec(dllimport) ULONG ulDataInDll;

if (ulDataInDll == 0L)   /*sample code fragment*/
```

С помощью КОНСТАНТЫ более опасно, так как если вы забыли использовать еще один уровень косвенности, может получить доступ к адресной таблицы импорта указатель на переменную, не саму переменную. Проблемы такого типа часто может проявиться как нарушение прав доступа, так как таблицу адресов импорта в настоящее время выполняется только для чтения, компилятор и компоновщик.

Текущий MSVC компоновщик выдаст предупреждение при обнаружении CONSTANT в DEF-файле для учетной записи для этого случая. Только для использования КОНСТАНТА том случае, если невозможно перекомпилировать некоторые объектный файл, в котором не указаны в файле заголовка **__declspec(dllimport)** на прототипе.

## <a name="see-also"></a>См. также

[Импорт в приложение](importing-into-an-application.md)
