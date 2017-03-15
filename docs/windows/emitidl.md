---
title: "emitidl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.emitidl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "emitidl attribute"
ms.assetid: 85b80c56-578e-4392-ac03-8443c74ebb7d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# emitidl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет, будут ли обработаны все последующие атрибуты IDL, а будут помещены в созданном файле idl.  
  
## Синтаксис  
  
```  
  
      [ emitidl([boolean],  
   defaultimports=[boolean]  
) ] ;  
```  
  
#### Параметры  
 `boolean`  
 Возможные значения: **true**"  **false**"  **forced**"  **restricted**"  **push**или  **шипучка**.  
  
-   If **true**все атрибуты категории IDL, обнаруженные в файле исходного кода будут помещены в созданном файле idl.  Это параметр по умолчанию emitidl.  
  
-   If **false**все атрибуты категории IDL, обнаруженные в файле исходного кода не будут помещены в созданном файле idl.  
  
-   If **restricted**позволяет атрибуты IDL, чтобы находиться в файле без a  [Модуль](../windows/module-cpp.md) атрибут.  Компилятор не создаст файл idl.  
  
-   If **forced**переопределяет последующее  **restricted** атрибут, который требует файла \- a  **Модуль** атрибут если атрибуты IDL в файле.  
  
-   **push** позволяет сохранять текущие  **emitidl** параметры внутренней  **emitidl** стек.  **шипучка** позволяет устанавливать  **emitidl** на любое значение в верхней части внутренней  **emitidl** стек.  
  
 **defaultimports**\=\[  `boolean`\(необязательно\)\]  
 -   If `boolean` существует  **true**, docobj.idl будет импортировано в созданный файл idl.  Кроме того, если в idl\-файл с таким же именем в файле, h, `#include` в свой исходный код находится в том же каталоге, что и файл .h, то созданный файл idl будут содержать выписку импорта в idl\-файл.  
  
-   If `boolean` существует  **false**, docobj.idl не импортировано в созданный файл idl.  Необходимо явно импортировать idl\-файлы с [импорт](../windows/import.md).  
  
## Заметки  
 После emitidl Атрибут C\+\+ обнаружен в файле исходного кода, атрибутах IDL категории будет помещен в созданном файле idl.  Если нет emitidl атрибут атрибуты IDL в файле исходного кода, будет выведен в созданный файл idl.  
  
 Можно иметь несколько emitidl атрибуты в файле исходного кода.  If `[emitidl(false)];` встречает в файле без последующего  `[emitidl(true)];`после этого атрибуты не обрабатываются в созданный файл idl.  
  
 Каждый раз, когда компилятор встречает новый файл **emitidl** неявно присваивается  **true**.  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Любой|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Stand\-Alone Attributes](../Topic/Stand-Alone%20Attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)