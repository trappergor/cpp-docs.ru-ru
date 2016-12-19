---
title: "version (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.version"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "version attribute"
  - "version information, version attribute"
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# version (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет конкретную версию среди нескольких версий класса.  
  
## Синтаксис  
  
```  
  
      [ version(  
   "version"  
) ]  
```  
  
#### Параметры  
 *версия*  
 Номер версии компонентного класса.  Если не указано, 1,0 будут помещены в idl\-файле.  
  
## Заметки  
 **версия** Атрибут C\+\+ имеет ту же функциональность, что и  [версия](http://msdn.microsoft.com/library/windows/desktop/aa367306) Атрибут MIDL и передается через к созданному файлу idl.  
  
## Пример  
 См. [bindable](../windows/bindable.md) пример использования образца  **версия**.  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**класс**"  `struct`|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|**CoClass**|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения о контекстах атрибута см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)