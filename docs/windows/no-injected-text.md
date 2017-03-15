---
title: "no_injected_text | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.no_injected_text"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "no_injected_text attribute"
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# no_injected_text
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Запрещает компилятору впрыскивать код в результате использования атрибута.  
  
## Синтаксис  
  
```  
  
      [ no_injected_text(  
   boolean  
) ];  
```  
  
#### Параметры  
 `boolean`\(необязательно\)  
 **true** если не требуется ни введенного кода  **false** включение код для вставки.  **true** значение по умолчанию.  
  
## Заметки  
 Наиболее распространенное использование **no\_injected\_text** атрибут C\+\+   [\/Fx](../build/reference/fx-merge-injected-code.md) параметр компилятора, который вставляет  **no\_injected\_text** атрибут в файл .mrg.  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Любой|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения о контекстах атрибута см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)