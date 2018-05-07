---
title: Класс COleBusyDialog | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleBusyDialog
- AFXODLGS/COleBusyDialog
- AFXODLGS/COleBusyDialog::COleBusyDialog
- AFXODLGS/COleBusyDialog::DoModal
- AFXODLGS/COleBusyDialog::GetSelectionType
- AFXODLGS/COleBusyDialog::m_bz
dev_langs:
- C++
helpviewer_keywords:
- COleBusyDialog [MFC], COleBusyDialog
- COleBusyDialog [MFC], DoModal
- COleBusyDialog [MFC], GetSelectionType
- COleBusyDialog [MFC], m_bz
ms.assetid: c881a532-9672-4c41-b51b-5ce4a7246a6b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b061d2cc31a67c2e6059abeaadb6062b77cacb88
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="colebusydialog-class"></a>Класс COleBusyDialog
Используется для диалоговых окон OLE "Сервер не отвечает" или "Сервер занят".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleBusyDialog : public COleDialog  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleBusyDialog::COleBusyDialog](#colebusydialog)|Создает объект `COleBusyDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleBusyDialog::DoModal](#domodal)|Отображает диалоговое окно OLE, сервер занят.|  
|[COleBusyDialog::GetSelectionType](#getselectiontype)|Определяет, выбранных в диалоговом окне.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleBusyDialog::m_bz](#m_bz)|Структура типа **OLEUIBUSY** , управляет поведением окна.|  
  
## <a name="remarks"></a>Примечания  
 Создание объекта класса `COleBusyDialog` при необходимости вызовите этим диалоговым окнам. После `COleBusyDialog` объект был создан, можно использовать [m_bz](#m_bz) структуры для инициализации значения или состояния элементов управления в диалоговом окне. `m_bz` Структуры имеет тип **OLEUIBUSY**. Дополнительные сведения об использовании этого класса диалогового окна см. в разделе [DoModal](#domodal) функции-члена.  
  
> [!NOTE]
>  Контейнер, созданный мастером код приложения использует этот класс.  
  
 Дополнительные сведения см. в разделе [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) структуры в Windows SDK.  
  
 Дополнительные сведения о конкретных OLE диалоговым окнам см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleBusyDialog`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxodlgs.h  
  
##  <a name="colebusydialog"></a>  COleBusyDialog::COleBusyDialog  
 Только эта функция создает `COleBusyDialog` объекта.  
  
```  
explicit COleBusyDialog(
    HTASK htaskBusy,  
    BOOL bNotResponding = FALSE,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *htaskBusy*  
 Дескриптор для задачи сервера, занят.  
  
 *bNotResponding*  
 Если **TRUE**, вместо диалоговым окном, сервер занят вызывает диалоговое окно не отвечает. Текст в диалоговом окне не отвечает немного отличается от формулировки в диалоговом окне, сервер занят и будет отключена кнопка "Отмена".  
  
 `dwFlags`  
 Создание флага. Может содержать ноль или более из следующих значений в сочетании с помощью оператора побитового или:  
  
- **BZ_DISABLECANCELBUTTON** отключить кнопку "Отмена", при вызове диалоговым окном.  
  
- **BZ_DISABLESWITCHTOBUTTON** отключить кнопку Перейти к при вызове диалоговым окном.  
  
- **BZ_DISABLERETRYBUTTON** отключить кнопку "Повторить", при вызове диалоговое окно.  
  
 `pParentWnd`  
 Указывает на объект window родительского или владелец (типа `CWnd`), которому принадлежит объект диалогового окна. Если это **NULL**, главное окно приложения имеет значение родительского окна объекта диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 Чтобы открыть диалоговое окно, вызовите [DoModal](#domodal).  
  
 Дополнительные сведения см. в разделе [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) структуры в Windows SDK.  
  
##  <a name="domodal"></a>  COleBusyDialog::DoModal  
 Эта функция вызывается для отображения диалогового окна OLE, сервер занят или сервер не отвечает.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние завершения для диалогового окна. Одно из следующих значений:  
  
- **IDOK** Если успешно откроется диалоговое окно.  
  
- **IDCANCEL** Если пользователь отменил это диалоговое окно.  
  
- **IDABORT** Если произошла ошибка. Если **IDABORT** будет возвращен, вызовите `COleDialog::GetLastError` функции-члена для получения дополнительных сведений о типе возникшей ошибки. Для получения списка возможных ошибок [OleUIBusy](http://msdn.microsoft.com/library/windows/desktop/ms680125) функции в Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 Если требуется инициализировать различные элементы управления диалоговых окон, задав члены [m_bz](#m_bz) структуры, это следует сделать до вызова метода `DoModal`, но после создания объекта диалогового окна.  
  
 Если `DoModal` возвращает **IDOK**, можно вызывать другой член функции для получения параметров или сведения, введенных пользователем в диалоговом окне.  
  
##  <a name="getselectiontype"></a>  COleBusyDialog::GetSelectionType  
 Эта функция вызывается для получения выбора типа, выбранного пользователем в диалоговом окне, сервер занят.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Тип выбора объектов.  
  
### <a name="remarks"></a>Примечания  
 Тип возвращаемого значения задаются **выбора** тип перечисления, объявленный в `COleBusyDialog` класса.  
  
```  
enum Selection {
    switchTo,
    retry,
    callUnblocked
    };
```  
  
 Выполните краткое описание каждого из этих значений.  
  
- **COleBusyDialog::switchTo** переключиться в кнопка была нажата.  
  
- **COleBusyDialog::retry** была нажата кнопка "Повторить".  
  
- **COleBusyDialog::callUnblocked** вызов, чтобы активировать сервер стал разблокирован.  
  
##  <a name="m_bz"></a>  COleBusyDialog::m_bz  
 Структура типа **OLEUIBUSY** используется для управления поведением диалогового окна «сервер занят».  
  
```  
OLEUIBUSY m_bz;  
```  
  
### <a name="remarks"></a>Примечания  
 Члены этой структуры можно изменить непосредственно или с помощью функций-членов.  
  
 Дополнительные сведения см. в разделе [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) структуры в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)
