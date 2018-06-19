---
title: Импорт с помощью DEF-файлы | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- importing DLLs [C++], DEF files
- def files [C++], importing with
- .def files [C++], importing with
- dllimport attribute [C++], DEF files
- DLLs [C++], DEF files
ms.assetid: aefdbf50-f603-488a-b0d7-ed737bae311d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b36a68267251f76294ec6f3a0391ffa5f259704c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368861"
---
# <a name="importing-using-def-files"></a>Импорт с помощью DEF-файлов
Если вы решили использовать **__declspec(dllimport)** вместе с DEF-файла, следует изменить файл .def для использования данных вместо КОНСТАНТА для уменьшения вероятности того, что неверный код вызовет ошибку:  
  
```  
// project.def  
LIBRARY project  
EXPORTS  
   ulDataInDll   DATA  
```  
  
 В следующей таблице описаны причины возникновения ошибки.  
  
|Ключевое слово|Создает в библиотеке импорта|Экспорт|  
|-------------|---------------------------------|-------------|  
|`CONSTANT`|`_imp_ulDataInDll`, `_ulDataInDll`|`_ulDataInDll`|  
|`DATA`|`_imp_ulDataInDll`|`_ulDataInDll`|  
  
 С помощью **__declspec(dllimport)** и КОНСТАНТЫ перечислены оба `imp` версии и внешнее имя в LIB-файле DLL импорта библиотеки, созданных для явного связывания. С помощью **__declspec(dllimport)** и списки данных просто `imp` версия имени.  
  
 При использовании КОНСТАНТЫ, одно из следующих конструкций кода может использоваться для доступа к `ulDataInDll`:  
  
```  
__declspec(dllimport) ULONG ulDataInDll; /*prototype*/  
if (ulDataInDll == 0L)   /*sample code fragment*/  
```  
  
 - или -  
  
```  
ULONG *ulDataInDll;      /*prototype*/  
if (*ulDataInDll == 0L)  /*sample code fragment*/  
```  
  
 Однако при использовании данных в DEF-файле только код, скомпилированный со следующим определением можно получить доступ к переменной `ulDataInDll`:  
  
```  
__declspec(dllimport) ULONG ulDataInDll;  
  
if (ulDataInDll == 0L)   /*sample code fragment*/  
```  
  
 Использование КОНСТАНТ в более рискованным, поскольку если забыт использовать дополнительный уровень косвенного обращения, может получить доступ к адресную таблицу импорта указатель на переменную, не саму переменную. Поскольку таблица адресов импорта в настоящее время устанавливаются только для чтения, компилятор и компоновщик проблемы такого типа часто проявляется как нарушение прав доступа.  
  
 Текущий компоновщик Visual C++ выдает предупреждение при обнаружении CONSTANT в DEF-файле для учетной записи для этого случая. Только использование CONSTANT том случае, если невозможно перекомпилировать некоторый объектный файл, в котором не указаны в файле заголовка **__declspec(dllimport)** в прототипе.  
  
## <a name="see-also"></a>См. также  
 [Импорт в приложение](../build/importing-into-an-application.md)
