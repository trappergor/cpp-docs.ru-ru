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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: a4c17a1da8d1be00ebff171af09bc6c8eb81ed44
ms.lasthandoff: 02/24/2017

---
# <a name="csimpledialog-class"></a>Класс CSimpleDialog
Этот класс реализует базовые модального диалогового окна.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <WORD t_wDlgTemplateID, BOOL t_bCenter = TRUE>  
class CSimpleDialog : public CDialogImplBase
```  
  
#### <a name="parameters"></a>Параметры  
 *t_wDlgTemplateID*  
  
 Идентификатор ресурса в ресурсе шаблона диалогового окна.  
  
 *t_bCenter*  
 **Значение TRUE,** Если объект диалоговое окно по центру в окне «владелец»; в противном случае **FALSE**.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSimpleDialog::DoModal](#domodal)|Создает модальное диалоговое окно.|  
  
## <a name="remarks"></a>Примечания  
 Реализует модального диалогового окна с базовыми функциями. `CSimpleDialog`предоставляет поддержку для общих элементов управления Windows только. Для создания и отображения модального диалогового окна, создайте экземпляр этого класса, указав имя существующего ресурса шаблона диалогового окна. Объект диалогового окна закрывается при щелчке любой элемент управления с помощью предварительно определенные значения (например, IDOK и IDCANCEL).  
  
 `CSimpleDialog`можно создавать только модальные диалоговые окна. `CSimpleDialog`предоставляет процедуру диалогового окна, который использует схему сообщений по умолчанию для направления сообщений для соответствующих обработчиков.  
  
 В разделе [реализация диалогового](../../atl/implementing-a-dialog-box.md) подробнее.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CDialogImplBase`  
  
 `CSimpleDialog`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="domodal"></a>CSimpleDialog::DoModal  
 Вызывает модального диалогового окна и возвращает результат диалогового окна после операции.  
  
```
INT_PTR DoModal(HWND hWndParent = ::GetActiveWindow());
```  
  
### <a name="parameters"></a>Параметры  
 `hWndParent`  
 Дескриптор родительского окна. Если значение не указано, родительский присваивается текущее активное окно.  
  
### <a name="return-value"></a>Возвращаемое значение  
 При успешном выполнении возвращается идентификатор ресурса для управления, закрыть диалоговое окно.  
  
 Если функция завершается с ошибкой, то возвращаемое значение –&1;. Чтобы получить расширенные сведения об ошибке, вызовите функцию `GetLastError`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод обрабатывает все взаимодействие с пользователем при активном диалоговом окне. Именно это и делает окно модальным; то есть до закрытия диалогового пользователь не может взаимодействовать с другими окнами.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

