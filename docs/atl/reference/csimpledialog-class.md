---
title: "Класс CSimpleDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleDialog
- ATLWIN/ATL::CSimpleDialog
- ATLWIN/ATL::CSimpleDialog::DoModal
dev_langs:
- C++
helpviewer_keywords:
- CSimpleDialog class
- CSimpleDialog class, modal dialog boxes in ATL
- dialog boxes, modal
- modal dialog boxes, ATL
ms.assetid: 2ae65cc9-4f32-4168-aecd-200b4a480fdf
caps.latest.revision: 19
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 2448f2fcd0547e2344dde51392873e3276f2bd09
ms.lasthandoff: 04/01/2017

---
# <a name="csimpledialog-class"></a>Класс CSimpleDialog
Этот класс реализует основные модального диалогового окна.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <WORD t_wDlgTemplateID, BOOL t_bCenter = TRUE>  
class CSimpleDialog : public CDialogImplBase
```  
  
#### <a name="parameters"></a>Параметры  
 *t_wDlgTemplateID*  
  
 Идентификатор ресурса ресурс шаблона диалоговых окон.  
  
 *t_bCenter*  
 **Значение TRUE,** Если объект диалоговое окно по центру на окно-владелец; в противном случае **FALSE**.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSimpleDialog::DoModal](#domodal)|Создает модальное диалоговое окно.|  
  
## <a name="remarks"></a>Примечания  
 Реализует модального диалогового окна с базовыми функциями. `CSimpleDialog`предоставляет поддержку для общих элементов управления Windows только. Для создания и отображения модального диалогового окна, создайте экземпляр этого класса, предоставив имя существующего ресурса шаблона диалогового окна. Объект диалогового окна закрывается при щелчке любого элемента управления с предварительно определенного значения (например IDOK или IDCANCEL).  
  
 `CSimpleDialog`можно создать только модальные диалоговые окна. `CSimpleDialog`предоставляет процедуру диалогового окна, который использует схему сообщений по умолчанию для направления сообщений для соответствующих обработчиков.  
  
 В разделе [реализация диалогового](../../atl/implementing-a-dialog-box.md) для получения дополнительной информации.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CDialogImplBase`  
  
 `CSimpleDialog`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="domodal"></a>CSimpleDialog::DoModal  
 Открывается модальное диалоговое окно и возвращает результат диалогового окна после завершения.  
  
```
INT_PTR DoModal(HWND hWndParent = ::GetActiveWindow());
```  
  
### <a name="parameters"></a>Параметры  
 `hWndParent`  
 Дескриптор родительского окна. Если значение не указано, родительский присваивается текущее активное окно.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращается идентификатор ресурса для элемента управления, которое диалоговое окно закрывается.  
  
 Если функция завершается с ошибкой, возвращается значение-1. Чтобы получить расширенные сведения об ошибке, вызовите функцию `GetLastError`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод обрабатывает все взаимодействие с пользователем во время активного диалоговым окном. Именно это и делает окно модальным; то есть пользователь не может взаимодействовать с других окон до закрытия диалогового.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

