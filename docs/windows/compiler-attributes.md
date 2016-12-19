---
title: "Compiler Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe compiler, attributes"
  - "attributes [C++], compiler"
ms.assetid: 53cd9bee-1521-48ec-b171-80feac2096cc
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Compiler Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Атрибуты компилятора предоставляют разнообразные возможности.  
  
|Атрибут|Описание|  
|-------------|--------------|  
|[emitidl](../windows/emitidl.md)|Определяет, будут ли обработаны все последующие атрибуты IDL, а будут помещены в созданном файле idl.|  
|[event\_receiver](../windows/event-receiver.md)|Создает приемник событий.|  
|[event\_source](../windows/event-source.md)|Создает источник события.|  
|[export](../windows/export.md)|Структура данных будет располагаться в idl\-файле.|  
|[implements](../Topic/implements%20\(C++\).md)|Определяет интерфейсы диспетчеризации, принуждаются, чтобы быть членами компонентного класса IDL.|  
|[importidl](../windows/importidl.md)|Вставляет указанный файл idl в созданный файл idl.|  
|[importlib](../windows/importlib.md)|Делает типы, которые уже компилировались в другой доступный создания библиотеки типов в библиотеке типов.|  
|[includelib](../windows/includelib-cpp.md)|Вызывает idl\-файл или .h, которые нужно включить в созданном файле idl.|  
|[library\_block](../windows/library-block.md)|Задает конструкцию внутри блока библиотеки файла idl.|  
|[no\_injected\_text](../windows/no-injected-text.md)|Запрещает компилятору впрыскивать код в результате использования атрибута.|  
|[satype](../windows/satype.md)|Указывает тип данных SAFEARRAY.|  
|[версия](../windows/version-cpp.md)|Определяет конкретную версию среди нескольких версий интерфейса или класса.|  
  
## См. также  
 [Attributes by Group](../windows/attributes-by-group.md)