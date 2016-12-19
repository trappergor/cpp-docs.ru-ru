---
title: "_U_STRINGorID Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL._U_STRINGorID"
  - "ATL::_U_STRINGorID"
  - "_U_STRINGorID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_U_STRINGorID class"
  - "U_STRINGorID class"
ms.assetid: 443cdc00-d265-4b27-8ef3-2feb95f3e5e3
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _U_STRINGorID Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс адаптера аргумента позволяет или имена ресурсов \(`LPCTSTR` s\) или идентификаторы ресурса \(**UINT** s\), передаваемые функции, не требуя вызывающий объект преобразовал идентификатор в строку с помощью **MAKEINTRESOURCE** макрос.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
class _U_STRINGorID  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[\_U\_STRINGorID::\_U\_STRINGorID](../Topic/_U_STRINGorID::_U_STRINGorID.md)|Конструктор.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[\_U\_STRINGorID::m\_lpstr](../Topic/_U_STRINGorID::m_lpstr.md)|Идентификатор ресурса.|  
  
## Заметки  
 Этот класс предназначен для реализации программы\-оболочки в API управления ресурсами Windows как функции [FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042), [LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072) и [LoadMenu](http://msdn.microsoft.com/library/windows/desktop/ms647990), которые принимают аргумент `LPCTSTR`, который может быть либо именем ресурса или по его идентификатору.  
  
 Класс определяет 2 перегруженные варианты конструктора: принять аргумент `LPCTSTR`, а второй принимает аргумент **UINT**.  Аргумент **UINT** преобразовать в совместимый тип ресурса с функциями управления ресурсами Windows, используя макрос **MAKEINTRESOURCE** и результат, хранящиеся в элементе данных одного типа, [m\_lpstr](../Topic/_U_STRINGorID::m_lpstr.md).  Аргумент конструктора `LPCTSTR` хранятся непосредственно без преобразования.  
  
## Требования  
 **Header:**  atlwin.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)