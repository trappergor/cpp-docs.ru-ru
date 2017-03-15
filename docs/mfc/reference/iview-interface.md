---
title: "Интерфейс IView | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IView
dev_langs:
- C++
helpviewer_keywords:
- views [MFC]
- IView class
- views, classes
ms.assetid: 9321f299-486e-4551-bee9-d2c4a7b91548
caps.latest.revision: 23
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 9a8b5f2d9d123aa3032cb30ecdbdd1cd380b32f8
ms.lasthandoff: 02/24/2017

---
# <a name="iview-interface"></a>Интерфейс IView
Реализует несколько методов, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) использует для отправки уведомлений элемента управления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
interface class IView  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IView::OnActivateView](#onactivateview)|Вызывается по MFC, когда представление активируется или деактивируется.|  
|[IView::OnInitialUpdate](#oninitialupdate)|Вызывается платформой после представления впервые присоединяется к документу, но до первоначального отображения представления.|  
|[IView::OnUpdate](#onupdate)|Вызывается методом MFC после изменения просмотр документа; Эта функция позволяет представлению обновления экрана для отражения изменений.|  
  
## <a name="remarks"></a>Примечания  
 `IView`реализует несколько методов, `CWinFormsView` использует для перенаправления общих уведомлений для размещенного элемента управления. Это [OnInitialUpdate](#oninitialupdate), [OnUpdate](#onupdate) и [OnActivateView](#onactivateview).  
  
 `IView`Аналогично [CView](../../mfc/reference/cview-class.md), но используется только с элементами управления и управляемых представлений.  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [использование пользовательского элемента управления формы Windows Form в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  

## <a name="requirements"></a>Требования  
 Заголовок: afxwinforms.h (определенный в сборке atlmfc\lib\mfcmifc80.dll)  

## <a name="a-nameonactivateviewa-iviewonactivateview"></a><a name="onactivateview"></a>IView::OnActivateView  
Вызывается по MFC, когда представление активируется или деактивируется.
```
void OnActivateView(bool activate);
```
## <a name="parameters"></a>Параметры
`activate`  
Указывает, является ли представление активируется или деактивируется.  

## <a name="a-nameoninitialupdatea-iviewoninitialupdate"></a><a name="oninitialupdate"></a>IView::OnInitialUpdate
Вызывается платформой после представления впервые присоединяется к документу, но до первоначального отображения представления.
```
void OnInitialUpdate();
```

## <a name="a-nameonupdatea-iviewonupdate"></a><a name="onupdate"></a>IView::OnUpdate 
После изменения просмотр документа вызван MFC.  
```
void OnUpdate();
```
## <a name="remarks"></a>Примечания  
Эта функция позволяет представлению обновления экрана для отражения изменений.

## <a name="see-also"></a>См. также  
 [Класс CWinFormsView](../../mfc/reference/cwinformsview-class.md)   
 [CView-класс](../../mfc/reference/cview-class.md)

