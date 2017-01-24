---
title: "rename (#import) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Rename"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "rename - атрибут"
ms.assetid: 5c5c6153-1087-4b7b-87fb-fc59b90b9975
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# rename (#import)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к языку C\+\+**  
  
 Обходит проблемы конфликтов имен.  
  
## Синтаксис  
  
```  
rename("OldName","NewName")  
```  
  
#### Параметры  
 `OldName`  
 Старое имя в библиотеке типов.  
  
 `NewName`  
 Имя, используемое вместо старого имени.  
  
## Заметки  
 Если этот атрибут задан, компилятор заменяет все вхождения *OldName* в библиотеке типов предоставленным пользователем именем *NewName* в результирующих файлах заголовка.  
  
 Этот атрибут может использоваться, если имя в библиотеке типов совпадает с определением макроса в системных файлах заголовка.  Если проблема не устранена, будут созданы различные синтаксические ошибки, например [Ошибка компилятора C2059](../Topic/Compiler%20Error%20C2059.md) и [Ошибка компилятора C2061](../error-messages/compiler-errors-1/compiler-error-c2061.md).  
  
> [!NOTE]
>  Замена предоставляется для имени, используемого в библиотеке типов, а не для имени, используемого в открывшемся файле заголовка.  
  
 Например, предположим, что свойство `MyParent` существует в библиотеке типов, а макрос `GetMyParent` определен в файле заголовка и используется перед `#import`.  Поскольку `GetMyParent` — имя по умолчанию функции\-оболочки для свойства **get** обработки ошибок, возникает конфликт имен.  Для решения проблемы используйте следующий атрибут в инструкции `#import`:  
  
```  
rename("MyParent","MyParentX")  
```  
  
 чтобы переименовать имя `MyParent` в библиотеке типов.  Попытка переименовать программу\-оболочку `GetMyParent` завершится ошибкой:  
  
```  
rename("GetMyParent","GetMyParentX")  
```  
  
 Это происходит потому, что имя `GetMyParent` может возникать только в открывшемся файле заголовка библиотеки типов.  
  
 **Завершение блока, относящегося только к языку C\+\+**  
  
## См. также  
 [Атрибуты \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [Директива \#import](../Topic/%23import%20Directive%20\(C++\).md)