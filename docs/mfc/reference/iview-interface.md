---
title: "Интерфейс IView | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IView
- AFXWINFORMS/IView
- AFXWINFORMS/IView::OnActivateView
- AFXWINFORMS/IView::OnInitialUpdate
- AFXWINFORMS/IView::OnUpdate
dev_langs:
- C++
helpviewer_keywords:
- views [MFC]
- IView class [MFC]
- views [MFC], classes
ms.assetid: 9321f299-486e-4551-bee9-d2c4a7b91548
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a4266d8f5ec564dac67d7167c6c9bab4768a0276
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="iview-interface"></a>Интерфейс IView
Реализует несколько методов, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) использует для отправки уведомлений управляемого элемента управления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
interface class IView  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IView::OnActivateView](#onactivateview)|Вызывается средой MFC, когда представление активируется или деактивируется.|  
|[IView::OnInitialUpdate](#oninitialupdate)|Вызывается платформой после представление впервые присоединяется к документу, но до первоначального отображения представления.|  
|[IView::OnUpdate](#onupdate)|Вызывается методом MFC после изменения представления документа; Эта функция обеспечивает представление, чтобы обновить его отображение, чтобы отразить изменения.|  
  
## <a name="remarks"></a>Примечания  
 `IView`реализует несколько методов, `CWinFormsView` используется для перенаправления общих уведомлений для размещенного управляемого элемента управления. Это [OnInitialUpdate](#oninitialupdate), [OnUpdate](#onupdate) и [OnActivateView](#onactivateview).  
  
 `IView`Аналогично [CView](../../mfc/reference/cview-class.md), но используется только с управляемых представления и элементы управления.  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [с помощью пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  

## <a name="requirements"></a>Требования  
 Заголовок: afxwinforms.h (определенный в сборке atlmfc\lib\mfcmifc80.dll)  

## <a name="onactivateview"></a>IView::OnActivateView  
Вызывается средой MFC, когда представление активируется или деактивируется.
```
void OnActivateView(bool activate);
```
## <a name="parameters"></a>Параметры
`activate`  
Указывает, является ли представление активируется или деактивируется.  

## <a name="oninitialupdate"></a>IView::OnInitialUpdate
Вызывается платформой после представление впервые присоединяется к документу, но до первоначального отображения представления.
```
void OnInitialUpdate();
```

## <a name="onupdate"></a>IView::OnUpdate 
После изменения представления документа вызван MFC.  
```
void OnUpdate();
```
## <a name="remarks"></a>Примечания  
Эта функция обеспечивает представление, чтобы обновить его отображение, чтобы отразить изменения.

## <a name="see-also"></a>См. также  
 [Класс CWinFormsView](../../mfc/reference/cwinformsview-class.md)   
 [Класс CView](../../mfc/reference/cview-class.md)
