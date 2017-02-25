---
title: "CSmartDockingInfo Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSmartDockingInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSmartDockingInfo class"
ms.assetid: cab04f38-4bc1-4378-9337-c56fc87fbd68
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# CSmartDockingInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет внешний вид меток умных закрепления.  
  
## Синтаксис  
  
```  
class CSmartDockingInfo : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|`CSmartDockingInfo::CSmartDockingInfo`|Конструктор по умолчанию.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSmartDockingInfo::CopyTo](../Topic/CSmartDockingInfo::CopyTo.md)|Копирует текущие интеллектуальные параметры данных закрепления в предоставленный объект [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md).|  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CSmartDockingInfo::m\_bUseThemeColorInShading](../Topic/CSmartDockingInfo::m_bUseThemeColorInShading.md)|Указывает, использовать ли текущий цвет из темы, когда границы отображаются интеллектуальные маркеры закрепления.|  
|[CSmartDockingInfo::m\_clrBaseBackground](../Topic/CSmartDockingInfo::m_clrBaseBackground.md)|Определяет базовый цвет фона умных меток закрепления.|  
|[CSmartDockingInfo::m\_clrToneDest](../Topic/CSmartDockingInfo::m_clrToneDest.md)|Определяет цвет, заменяющий `m_clrToneSrc` в умных растровых изображениях маркеры закрепления.|  
|[CSmartDockingInfo::m\_clrToneSrc](../Topic/CSmartDockingInfo::m_clrToneSrc.md)|Задает ключ цвета умных растровых изображений маркеры закрепления.|  
|[CSmartDockingInfo::m\_clrTransparent](../Topic/CSmartDockingInfo::m_clrTransparent.md)|Задает ключ цвета умных растровых изображений маркеры закрепления, когда они прозрачным.|  
|[CSmartDockingInfo::m\_nCentralGroupOffset](../Topic/CSmartDockingInfo::m_nCentralGroupOffset.md)|Определяет смещение центральной группы в составе интеллектуальные маркеры закрепления из центрального границ прямоугольника группы.|  
|[CSmartDockingInfo::m\_sizeTotal](../Topic/CSmartDockingInfo::m_sizeTotal.md)|Определяет общий размер всех умных меток закрепления в группе.|  
|[CSmartDockingInfo::m\_uiMarkerBmpResID](../Topic/CSmartDockingInfo::m_uiMarkerBmpResID.md)|Определяет идентификаторы ресурсов растровых изображений, инфраструктура использует для умных меток закрепления, которые не выделены.|  
|[CSmartDockingInfo::m\_uiMarkerLightBmpResID](../Topic/CSmartDockingInfo::m_uiMarkerLightBmpResID.md)|Определяет идентификаторы ресурсов растровых изображений, инфраструктура использует для умных меток закрепления, выделены.|  
  
## Заметки  
 Границы обрабатывают интеллектуальные маркеры закрепления для внутреннего использования.  На следующей иллюстрации показаны стандартные интеллектуальные маркеры закрепления.  
  
 ![Стандартные маркеры смарт&#45;закрепления](../../mfc/reference/media/nextsdmarkers.png "nextSDmarkers")  
  
 На данном рисунке образ слева указывает на метку закрепления центральной группы умную, не имеющий включенной закрепление на вкладке.  Образ в середине указывает правому краю умную маркер закрепления.  Образ справа указывает на метку закрепления центральной группы умную с включенной закрепление на вкладке.  Маркер закрепления центральной группы интеллектуального имеет основной растровое изображение и 5 интеллектуальные маркеры закрепления растровых изображений.  
  
 Можно настраивать следующие параметры умных меток закрепления.  
  
-   Цвет.  Например, можно заменить синий цвет меток в диаграмме с любыми определяемыми пользователем цветом.  
  
-   Цвет прозрачности.  
  
-   Смещение умной закрепления метки в центральной группе от границы ограничивающего прямоугольника.  
  
-   В основном растровое изображение, представляющий центральную группу.  
  
-   Растровые изображения, представляющий обычный и выбранных умных меток закрепления.  
  
 На следующем рисунке показан пример умных меток закрепления, которые были настроены:  
  
 ![Пользовательские маркеры смарт&#45;закрепления](../Image/nextSDmarkersCustom.png "nextSDmarkersCustom")  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)  
  
## Требования  
 **заголовок:** afxDockingManager.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CObject Class](../Topic/CObject%20Class.md)