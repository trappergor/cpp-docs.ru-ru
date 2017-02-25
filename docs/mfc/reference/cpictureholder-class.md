---
title: "CPictureHolder Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "Picture"
  - "CPictureHolder"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "элементы управления [MFC], OLE"
  - "CPictureHolder class"
  - "элементы управления OLE, изображение"
  - "Picture property"
ms.assetid: a4f59775-704a-41dd-b5bd-2e531c95127a
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CPictureHolder Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует свойства изображения, позволяющее пользователю для отображения изображения в элементе управления.  
  
## Синтаксис  
  
```  
class CPictureHolder  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CPictureHolder::CPictureHolder](../Topic/CPictureHolder::CPictureHolder.md)|Создает объект `CPictureHolder`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CPictureHolder::CreateEmpty](../Topic/CPictureHolder::CreateEmpty.md)|Создает пустой объект `CPictureHolder`.|  
|[CPictureHolder::CreateFromBitmap](../Topic/CPictureHolder::CreateFromBitmap.md)|Создает объект `CPictureHolder` из растрового изображения.|  
|[CPictureHolder::CreateFromIcon](../Topic/CPictureHolder::CreateFromIcon.md)|Создает объект `CPictureHolder` от значка.|  
|[CPictureHolder::CreateFromMetafile](../Topic/CPictureHolder::CreateFromMetafile.md)|Создает объект `CPictureHolder` из метафайла.|  
|[CPictureHolder::GetDisplayString](../Topic/CPictureHolder::GetDisplayString.md)|Извлекает строку, отображаемой в обозревателе свойств контейнера элемента управления.|  
|[CPictureHolder::GetPictureDispatch](../Topic/CPictureHolder::GetPictureDispatch.md)|Возвращает интерфейс `IDispatch` объекта `CPictureHolder`.|  
|[CPictureHolder::GetType](../Topic/CPictureHolder::GetType.md)|Указывает, является ли объект `CPictureHolder` растровое изображение, метафайл или значок.|  
|[CPictureHolder::Render](../Topic/CPictureHolder::Render.md)|Отображает изображение.|  
|[CPictureHolder::SetPictureDispatch](../Topic/CPictureHolder::SetPictureDispatch.md)|Задает интерфейс `IDispatch` объекта `CPictureHolder`.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CPictureHolder::m\_pPict](../Topic/CPictureHolder::m_pPict.md)|Указатель на объект изображения.|  
  
## Заметки  
 `CPictureHolder` не имеет базовый класс.  
  
 С помощью свойства изображения акций, разработчик может указать растровое изображение, значок или метафайл для отображения.  
  
 Дополнительные сведения о создании пользовательских свойства изображения см. в разделе [Элементы управления ActiveX MFC: Использование изображения в элементе управления ActiveX](../../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md) статьи.  
  
## Иерархия наследования  
 `CPictureHolder`  
  
## Требования  
 **Header:**  afxctl.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CFontHolder Class](../../mfc/reference/cfontholder-class.md)