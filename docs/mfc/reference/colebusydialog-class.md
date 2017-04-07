---
title: "Класс COleBusyDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- Server Not Responding dialog box
- Server Busy dialog box
- COleBusyDialog class
ms.assetid: c881a532-9672-4c41-b51b-5ce4a7246a6b
caps.latest.revision: 22
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 0c3ed264cdb83bc97337f13279a20f26b21d454b
ms.lasthandoff: 02/24/2017

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
|[COleBusyDialog::DoModal](#domodal)|Отображение диалогового окна OLE, сервер занят.|  
|[COleBusyDialog::GetSelectionType](#getselectiontype)|Определяет выбор, сделанный в диалоговом окне.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleBusyDialog::m_bz](#m_bz)|Структура типа **OLEUIBUSY** , контролирует поведение диалогового окна.|  
  
## <a name="remarks"></a>Примечания  
 Создание объекта класса `COleBusyDialog` используется для вызова этих диалоговых окон. После `COleBusyDialog` объект был создан, можно использовать [m_bz](#m_bz) структуры для инициализации значения или состояния элементов управления в диалоговом окне. `m_bz` Структуры имеет тип **OLEUIBUSY**. Дополнительные сведения об использовании этого класса диалогового окна в разделе [DoModal](#domodal) функции-члена.  
  
> [!NOTE]
>  Контейнер, созданный мастером код приложения использует этот класс.  
  
 Дополнительные сведения см. в разделе [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения о диалоговых окнах OLE конкретных см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).  
  
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
  
##  <a name="colebusydialog"></a>COleBusyDialog::COleBusyDialog  
 Эта функция создает только `COleBusyDialog` объекта.  
  
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
 Если **TRUE**, вызовите диалоговое окно не отвечает вместо диалогового окна, сервер занят. Текст в диалоговом окне не отвечает немного отличается от текст в диалоговом окне сервер занят, и отключить кнопку "Отмена".  
  
 `dwFlags`  
 Создание флага. Может содержать ноль или несколько из следующих значений, объединенных с оператор побитового или:  
  
- **BZ_DISABLECANCELBUTTON** отключить кнопку отмены при вызове диалоговое окно.  
  
- **BZ_DISABLESWITCHTOBUTTON** отключить кнопку Перейти к при вызове диалоговое окно.  
  
- **BZ_DISABLERETRYBUTTON** Отключение кнопки "Повторить", при вызове диалоговое окно.  
  
 `pParentWnd`  
 Указывает на объект окна родительского или владелец (типа `CWnd`), которому принадлежит объект диалогового окна. Если это **NULL**, главное окно приложения имеет значение родительского окна объекта диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 Чтобы открыть диалоговое окно, вызовите [DoModal](#domodal).  
  
 Дополнительные сведения см. в разделе [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="domodal"></a>COleBusyDialog::DoModal  
 Эта функция вызывается для отображения диалогового окна OLE, сервер занят или сервер не отвечает.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние завершения для диалогового окна. Одно из следующих значений:  
  
- **IDOK** Если успешно откроется диалоговое окно.  
  
- **IDCANCEL** Если пользователь отменил диалоговое окно.  
  
- **IDABORT** произошла ошибка. Если **IDABORT** будет возвращен, вызовите `COleDialog::GetLastError` функции-члена для получения дополнительных сведений о типе возникшей ошибки. Список возможных ошибок см. в разделе [OleUIBusy](http://msdn.microsoft.com/library/windows/desktop/ms680125) работать в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Если требуется инициализировать различные диалоговыми окнами, задав члены [m_bz](#m_bz) структуры, это следует сделать до вызова метода `DoModal`, но после создания объекта диалогового окна.  
  
 Если `DoModal` возвращает **IDOK**, можно вызвать другой член функции для получения параметров или данных, введенных пользователем в диалоговом окне.  
  
##  <a name="getselectiontype"></a>COleBusyDialog::GetSelectionType  
 Эта функция вызывается для получения тип выбора, выбранного пользователем в диалоговом окне, сервер занят.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Тип выбора, сделанного.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемый тип значений определяется **выбора** перечисления тип, объявленный в `COleBusyDialog` класса.  
  
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
  
- **COleBusyDialog::callUnblocked** вызова для активации сервера уже разблокирован.  
  
##  <a name="m_bz"></a>COleBusyDialog::m_bz  
 Структура типа **OLEUIBUSY** используется для управления поведением диалогового окна «сервер занят».  
  
```  
OLEUIBUSY m_bz;  
```  
  
### <a name="remarks"></a>Примечания  
 Члены этой структуры можно изменить непосредственно или с помощью функций-членов.  
  
 Дополнительные сведения см. в разделе [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)

