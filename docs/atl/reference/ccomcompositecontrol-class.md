---
title: "CComCompositeControl Class | Microsoft Docs"
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
  - "CComCompositeControl"
  - "ATL::CComCompositeControl"
  - "ATL.CComCompositeControl<T>"
  - "ATL.CComCompositeControl"
  - "ATL::CComCompositeControl<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComCompositeControl class"
  - "составные элементы управления, CComCompositeControl class"
ms.assetid: 1304b931-27e8-4fbc-be8e-bb226ad887fb
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComCompositeControl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет методы, необходимые для реализации составного элемента управления.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
      template <  
class T   
>  
class CComCompositeControl :  
public CComControl< T, CAxDialogImpl< T > >  
```  
  
#### Параметры  
 `T`  
 Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), а также от других интерфейсов требуется поддержка для составного элемента управления.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComCompositeControl::CComCompositeControl](../Topic/CComCompositeControl::CComCompositeControl.md)|Конструктор.|  
|[CComCompositeControl::~CComCompositeControl](../Topic/CComCompositeControl::~CComCompositeControl.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComCompositeControl::AdviseSinkMap](../Topic/CComCompositeControl::AdviseSinkMap.md)|Вызовите этот метод, чтобы advise или unadvise все элементы управления, которые размещение составного элемента управления.|  
|[CComCompositeControl::CalcExtent](../Topic/CComCompositeControl::CalcExtent.md)|Вызовите этот метод, чтобы вычислить размер в единицах диалогового окна **HIMETRIC** ресурса, используемого для размещения составного элемента управления.|  
|[CComCompositeControl::Create](../Topic/CComCompositeControl::Create.md)|Этот метод вызывается для создания окна элемента управления для составного элемента управления.|  
|[CComCompositeControl::CreateControlWindow](../Topic/CComCompositeControl::CreateControlWindow.md)|Вызывайте этот метод для создания окна элемента управления и advise любой элемент управления ведущего приложения.|  
|[CComCompositeControl::SetBackgroundColorFromAmbient](../Topic/CComCompositeControl::SetBackgroundColorFromAmbient.md)|Вызовите этот метод, чтобы задать цвет фона составного элемента управления с помощью цвета фона контейнера.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CComCompositeControl::m\_hbrBackground](../Topic/CComCompositeControl::m_hbrBackground.md)|Кисть фона.|  
|[CComCompositeControl::m\_hWndFocus](../Topic/CComCompositeControl::m_hWndFocus.md)|Дескриптор окна, которое в данный момент имеет фокус.|  
  
## Заметки  
 Классы, производные от класса `CComCompositeControl` наследует функциональные возможности составного элемента управления ActiveX.  Элементы управления ActiveX, производные от `CComCompositeControl` хозяйничаются стандартным диалоговым окном.  Эти типы элементов управления называются составными элементами управления, так как они смогут размещения других элементов управления \(элементов управления Windows собственного и управления ActiveX\).  
  
 `CComCompositeControl` определяет ресурс диалогового окна для использования в создании составной элемент управления, выполняя поиск перечисляемый член данных в классе дочернего элемента.  Элемент IDD этого класса дочернего элемента ему присваивается идентификатор ресурса ресурсов диалоговых окон, который будет использоваться в качестве окна элемента управления.  Ниже приведен пример элемента данных, который класс, производный от `CComCompositeControl` должен содержать, чтобы определить ресурс диалогового окна для окна элемента управления:  
  
 [!code-cpp[NVC_ATL_COM#13](../../atl/codesnippet/CPP/ccomcompositecontrol-class_1.h)]  
  
> [!NOTE]
>  Составные элементы управления всегда оконного элемента управления, хотя они могут содержать безоконные элементы управления.  
  
 Элемент управления, на который `CComCompositeControl`\- производный класс имеет расширение функциональности по умолчанию нашивая построенный.  Если элемент управления получает фокус, быть нашитым к внутри вмещающей приложение, нажав клавиши TAB можно последовательно вызывает фокус быть задействованным с помощью элементов управления всего составного элемента управления, содержащиеся, затем из составного элемента управления и к следующему элементу в последовательности табуляции контейнера.  Последовательность табуляции элементов управления диалогового окна размещенного определяется ресурсом и определяет порядок, в котором переход.  
  
> [!NOTE]
>  Сочетания клавиш для правильной работы с `CComCompositeControl`, должна быть загружена в таблицу сочетаний клавиш как создать элемент управления, передает дескриптор и число ускорителей обратно в [IOleControlImpl::GetControlInfo](../Topic/IOleControlImpl::GetControlInfo.md), а затем удаляет таблицу, если элемент управления освободить.  
  
## Пример  
 [!code-cpp[NVC_ATL_COM#14](../../atl/codesnippet/CPP/ccomcompositecontrol-class_2.h)]  
  
## Иерархия наследования  
 `WinBase`  
  
 [CComControlBase](../Topic/CComControlBase%20Class.md)  
  
 [CComControl](../../atl/reference/ccomcontrol-class.md)  
  
 `CComCompositeControl`  
  
## Требования  
 **Header:**  atlctl.h  
  
## См. также  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [Основные сведения о составном элементе управления](../Topic/ATL%20Composite%20Control%20Fundamentals.md)   
 [Class Overview](../../atl/atl-class-overview.md)