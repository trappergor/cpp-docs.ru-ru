---
title: Класс COleBusyDialog | Документация Майкрософт
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
ms.openlocfilehash: 5f9ed49115a82f6e032404b862b8eca0ad922a34
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37853073"
---
# <a name="colebusydialog-class"></a>Класс COleBusyDialog
Используется для диалоговых окон OLE "Сервер не отвечает" или "Сервер занят".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleBusyDialog : public COleDialog  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleBusyDialog::COleBusyDialog](#colebusydialog)|Создает объект `COleBusyDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleBusyDialog::DoModal](#domodal)|Отображает диалоговое окно OLE сервер занят.|  
|[COleBusyDialog::GetSelectionType](#getselectiontype)|Определяет выбора, сделанного в диалоговом окне.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleBusyDialog::m_bz](#m_bz)|Структура типа OLEUIBUSY, которое управляет поведением окна.|  
  
## <a name="remarks"></a>Примечания  
 Создайте объект класса `COleBusyDialog` при необходимости вызовите этим диалоговым окнам. После `COleBusyDialog` объект был создан, можно использовать [m_bz](#m_bz) структуры для инициализации значения или состояния элементов управления в диалоговом окне. `m_bz` Структуры имеет тип OLEUIBUSY. Дополнительные сведения об использовании этого класса диалогового окна см. в разделе [DoModal](#domodal) функция-член.  
  
> [!NOTE]
>  Контейнер, созданный мастером код приложения использует этот класс.  
  
 Дополнительные сведения см. в разделе [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) структуры в пакете Windows SDK.  
  
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
 Эта функция только создает `COleBusyDialog` объекта.  
  
```  
explicit COleBusyDialog(
    HTASK htaskBusy,  
    BOOL bNotResponding = FALSE,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *htaskBusy*  
 Дескриптор серверной задачи, занят.  
  
 *bNotResponding*  
 Значение TRUE, если вызовите диалоговое окно не отвечает вместо окно сервер занят. Текст в диалоговом окне не отвечает немного отличается от формулировки в диалоговом окне сервер занят, и будет отключена кнопка "Отмена".  
  
 *dwFlags*  
 Флаг для создания. Может содержать ноль или более из следующих значений в сочетании с помощью оператора побитового или:  
  
- BZ_DISABLECANCELBUTTON Отключение кнопки "Отмена", при вызове диалоговое окно.  
  
- BZ_DISABLESWITCHTOBUTTON отключения кнопки Переключиться в при вызове диалоговое окно.  
  
- BZ_DISABLERETRYBUTTON отключить "Повторить", при вызове диалоговое окно.  
  
 *pParentWnd*  
 Указывает на объект окна родительский объект или владельца (типа `CWnd`), которому принадлежит объект диалогового окна. Если это значение NULL, родительское окно объекта диалогового окна будет присвоено главного окна приложения.  
  
### <a name="remarks"></a>Примечания  
 Чтобы отобразить диалоговое окно, вызовите [DoModal](#domodal).  
  
 Дополнительные сведения см. в разделе [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) структуры в пакете Windows SDK.  
  
##  <a name="domodal"></a>  COleBusyDialog::DoModal  
 Вызывайте эту функцию для отображения диалогового окна OLE сервер занят "или" сервер не отвечает.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние завершения для диалогового окна. Одно из следующих значений:  
  
- IDOK, если было успешно отображено диалоговое окно.  
  
- IDCANCEL, если пользователь отменил диалоговое окно.  
  
- IDABORT, если произошла ошибка. Если возвращается IDABORT, вызовите `COleDialog::GetLastError` функция-член для получения дополнительных сведений о типе возникшей ошибки. Список возможных ошибок, см. в разделе [OleUIBusy](http://msdn.microsoft.com/library/windows/desktop/ms680125) функции в пакете Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 Если вы хотите инициализировать различных диалоговых путем определения участников [m_bz](#m_bz) структуры, это следует сделать до вызова метода `DoModal`, но после создания объекта диалогового окна.  
  
 Если `DoModal` возвращает IDOK, можно вызывать другой член функции для получения параметров или данных, введенных пользователем в диалоговом окне.  
  
##  <a name="getselectiontype"></a>  COleBusyDialog::GetSelectionType  
 Вызывайте эту функцию, чтобы получить тип выбора, выбранный пользователем в диалоговом окне сервер занят.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Тип выбора, сделанного.  
  
### <a name="remarks"></a>Примечания  
 Тип возвращаемого значения задаются `Selection` тип перечисления, объявленный в `COleBusyDialog` класса.  
  
```  
enum Selection {
    switchTo,
    retry,
    callUnblocked
    };
```  
  
 Выполните краткое описание каждого из этих значений.  
  
- `COleBusyDialog::switchTo` Переключиться в кнопка была нажата.  
  
- `COleBusyDialog::retry` Была нажата кнопка "Повторить".  
  
- `COleBusyDialog::callUnblocked` Вызов, чтобы активировать сервер уже разблокирован.  
  
##  <a name="m_bz"></a>  COleBusyDialog::m_bz  
 Структура типа OLEUIBUSY используется для управления поведением диалогового окна "сервер занят".  
  
```  
OLEUIBUSY m_bz;  
```  
  
### <a name="remarks"></a>Примечания  
 Члены этой структуры можно изменить непосредственно или с помощью функций-членов.  
  
 Дополнительные сведения см. в разделе [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) структуры в пакете Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)
