---
title: "Импорт с помощью DEF-файлов | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DEF-файлы [C++], импортирование из"
  - "DEF-файлы [C++], импортирование из"
  - "атрибут DllImport [C++], DEF-файлы"
  - "DLL-библиотеки [C++], DEF-файлы"
  - "импорт библиотек DLL [C++], DEF-файлы"
ms.assetid: aefdbf50-f603-488a-b0d7-ed737bae311d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Импорт с помощью DEF-файлов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При использовании **\_\_declspec\(dllimport\)** и DEF\-файла необходимо указать в DEF\-файле вместо ключевого слова CONSTANT ключевое слово DATA для уменьшения вероятности того, что неверный код вызовет ошибку:  
  
```  
// project.def  
LIBRARY project  
EXPORTS  
   ulDataInDll   DATA  
```  
  
 В следующей таблице описаны причины возникновения ошибки.  
  
|Ключевое слово|Возникает в импорте библиотеки|Экспортируется из|  
|--------------------|------------------------------------|-----------------------|  
|`CONSTANT`|`_imp_ulDataInDll_ulDataInDll`|`_ulDataInDll`|  
|`DATA`|`_imp_ulDataInDll`|`_ulDataInDll`|  
  
 Использование ключевого слова **\_\_declspec\(dllimport\)** и CONSTANT относится к обеим версиям `imp` и недекорируемому имени в LIB\-файле импорта библиотеки DLL, который создается для явного связывания.  Использование **\_\_declspec\(dllimport\)** и списка DATA относится только к версии имени `imp`.  
  
 При использовании CONSTANT любая из следующих конструкций кода может использоваться для доступа к `ulDataInDll`:  
  
```  
__declspec(dllimport) ULONG ulDataInDll; /*prototype*/  
if (ulDataInDll == 0L)   /*sample code fragment*/  
```  
  
 – или –  
  
```  
ULONG *ulDataInDll;      /*prototype*/  
if (*ulDataInDll == 0L)  /*sample code fragment*/  
```  
  
 Однако если в DEF\-файле используется DATA, то получить доступ к переменной `ulDataInDll` может только код, скомпилированный со следующим определением:  
  
```  
__declspec(dllimport) ULONG ulDataInDll;  
  
if (ulDataInDll == 0L)   /*sample code fragment*/  
```  
  
 Использовать CONSTANT более рискованно, потому что если забыть про использование высокого уровня косвенного обращения, то потенциально можно передать указатель адресной таблицы импорта переменной, а не саму переменную.  Проблема такого характера часто проявляется как нарушение прав доступа, т.к. компилятор или компоновщик делает адресную таблицу импорта в текущий момент доступной только для чтения.  
  
 При обнаружении CONSTANT в DEF\-файле текущий компоновщик Visual C\+\+ выдает предупреждение.  Использование CONSTANT оправданно в том случае, если невозможно перекомпилировать некоторый объектный файл, в котором в файле заголовка не указаны объявления с ключевым словом **\_\_declspec\(dllimport\)** в прототипе.  
  
## См. также  
 [Импорт в приложение](../build/importing-into-an-application.md)