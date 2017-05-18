---
title: "CDataExchange-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDataExchange
- AFXWIN/CDataExchange
- AFXWIN/CDataExchange::CDataExchange
- AFXWIN/CDataExchange::Fail
- AFXWIN/CDataExchange::PrepareCtrl
- AFXWIN/CDataExchange::PrepareEditCtrl
- AFXWIN/CDataExchange::PrepareOleCtrl
- AFXWIN/CDataExchange::m_bSaveAndValidate
- AFXWIN/CDataExchange::m_pDlgWnd
dev_langs:
- C++
helpviewer_keywords:
- DDX/DDV, Technical Note 26
- DDX/DDV, CDataExchange class
- DDX (dialog data exchange), direction of exchange
- DDX (dialog data exchange), between dialog and CDialog
- DDX (dialog data exchange), custom DDX routines
- DDV (dialog data validation)
- m_bSaveAndValidate
- CDataExchange class
- exchanging data between dialogs and CDialogs
- DDV (dialog data validation), custom DDV routines
- DDX/DDV
- DDX (dialog data exchange)
- validating data, dialog box data entry
ms.assetid: 84ed6113-325d-493e-a75d-223f03a992b8
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 8f35e87d562a894411401755ccd4fdd54e43b58a
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cdataexchange-class"></a>CDataExchange-класс
Поддерживает процедуры обмена данными диалогового окна (DDX) и проверки данных диалогового окна (DDV), используемые классами Microsoft Foundation.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDataExchange  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDataExchange::CDataExchange](#cdataexchange)|Создает объект `CDataExchange`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDataExchange::Fail](#fail)|Вызывается при сбое проверки. Сбрасывает фокуса к предыдущему элементу управления и вызывает исключение.|  
|[CDataExchange::PrepareCtrl](#preparectrl)|Подготавливает заданный элемент управления для обмена данными и проверки. Использование элементов управления nonedit.|  
|[CDataExchange::PrepareEditCtrl](#prepareeditctrl)|Подготавливает управления редактирования для обмена данными и проверки.|  
|[CDataExchange::PrepareOleCtrl](#prepareolectrl)|Подготавливает указанного элемента управления OLE для обмена данными и проверки. Использование элементов управления nonedit.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDataExchange::m_bSaveAndValidate](#m_bsaveandvalidate)|Флаг, указывающий направление DDX и DDV.|  
|[CDataExchange::m_pDlgWnd](#m_pdlgwnd)|Диалоговое окно или окно, где обмен данными выполняется.|  
  
## <a name="remarks"></a>Примечания  
 `CDataExchange`не имеет базового класса.  
  
 Этот класс используется при создании процедуры обмена данными для пользовательских типов данных или элементов управления, или если вы пишете собственные процедуры проверки данных. Дополнительные сведения о создании собственных процедур DDX и DDV см. в разделе [Технические заметки 26](../../mfc/tn026-ddx-and-ddv-routines.md). Обзор DDX и DDV см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md) и [диалоговые окна](../../mfc/dialog-boxes.md).  
  
 Объект `CDataExchange` предоставляет сведения о контексте, необходимых для DDX и DDV вступили. Флаг `m_bSaveAndValidate` — **FALSE** при использовании DDX для заполнения начального значения элементов управления диалогового окна из элементов данных. Флаг `m_bSaveAndValidate` — **TRUE** при использовании DDX устанавливаемое текущие значения элементов управления диалоговых окон в данные-члены и когда DDV используется для проверки значений данных. DDV проверка завершается неудачно, процедура DDV отобразится сообщение, описывающее ошибку ввода. Затем вызывается процедура DDV **сбой** Сброс фокуса в элемент управления, вызвавший ошибку и выдается исключение для остановки процесса проверки.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CDataExchange`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="cdataexchange"></a>CDataExchange::CDataExchange  
 Вызов этой функции-члена для создания `CDataExchange` объекта.  
  
```  
CDataExchange(
    CWnd* pDlgWnd,  
    BOOL bSaveAndValidate);
```  
  
### <a name="parameters"></a>Параметры  
 *pDlgWnd*  
 Указатель на родительское окно, содержащей элемент управления. Обычно это [CDialog](../../mfc/reference/cdialog-class.md)-производный объект.  
  
 `bSaveAndValidate`  
 Если **TRUE**, этот объект выполняет проверку данных, а затем записывает данные из элементов управления к элементам. Если **FALSE**, этот объект будет переместить данные из членов для элементов управления.  
  
### <a name="remarks"></a>Примечания  
 Создать `CDataExchange` объект для хранения дополнительной информации в объекте данных exchange для передачи к окну [CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange) функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCControlLadenDialog&#70;](../../mfc/codesnippet/cpp/cdataexchange-class_1.cpp)]  
  
##  <a name="fail"></a>CDataExchange::Fail  
 Платформа вызывает эту функцию-член, при сбое операции проверки (DDV) данных диалогового окна.  
  
```  
void Fail();
```  
  
### <a name="remarks"></a>Примечания  
 **Сбой** восстанавливает фокуса и выделения для элемента управления, сбой которого проверки (если элемент управления для восстановления). **Сбой** создаст исключение типа [CUserException](../../mfc/reference/cuserexception-class.md) для остановки процесса проверки. Исключение в результате сообщение, описывающее ошибку для отображения. После сбоя проверки DDV пользователя можно повторить ввод данных в элемент управления, вызвавший ошибку.  
  
 Средства реализации пользовательских процедур DDV можно вызвать **сбой** из своих программах при сбое проверки.  
  
 Дополнительные сведения о создании собственных процедур DDX и DDV см. в разделе [Технические заметки 26](../../mfc/tn026-ddx-and-ddv-routines.md). Обзор DDX и DDV см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md) и [диалоговому](../../mfc/dialog-boxes.md).  
  
##  <a name="m_bsaveandvalidate"></a>CDataExchange::m_bSaveAndValidate  
 Этот флаг указывает направление операции с данными exchange (DDX) диалогового окна.  
  
```  
BOOL m_bSaveAndValidate;  
```  
  
### <a name="remarks"></a>Примечания  
 Флаг ненулевое значение, если `CDataExchange` объект используется для перемещения данных из элементов управления диалоговых окон на данные-члены класса диалогового окна после пользователь редактирует элементов управления. Флаг равен нулю, если объект используется для инициализации элементов управления диалоговых окон с данные-члены класса диалогового окна.  
  
 Флаг также ненулевое значение во время проверки данных диалогового окна (DDV).  
  
 Дополнительные сведения о создании собственных процедур DDX и DDV см. в разделе [Технические заметки 26](../../mfc/tn026-ddx-and-ddv-routines.md). Обзор DDX и DDV см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md) и [диалоговому](../../mfc/dialog-boxes.md).  
  
##  <a name="m_pdlgwnd"></a>CDataExchange::m_pDlgWnd  
 Содержит указатель на [CWnd](../../mfc/reference/cwnd-class.md) объекта, для какой диалог обмен данными (диалоговых окон DDX) или проверки (DDV) выполняется.  
  
```  
CWnd* m_pDlgWnd;  
```  
  
### <a name="remarks"></a>Примечания  
 Обычно этот объект — [CDialog](../../mfc/reference/cdialog-class.md) объекта. Средства реализации пользовательских процедур DDX и DDV позволяет получить доступ к диалоговое окно, которое содержит элементы управления они работают на этот указатель.  
  
 Дополнительные сведения о создании собственных процедур DDX и DDV см. в разделе [Технические заметки 26](../../mfc/tn026-ddx-and-ddv-routines.md). Обзор DDX и DDV см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md) и [диалоговому](../../mfc/dialog-boxes.md).  
  
##  <a name="preparectrl"></a>CDataExchange::PrepareCtrl  
 Платформа вызывает эту функцию-член для подготовки указанного элемента управления для обмена данными диалогового окна (DDX) и проверки (DDV).  
  
```  
HWND PrepareCtrl(int nIDC);
```  
  
### <a name="parameters"></a>Параметры  
 `nIDC`  
 Идентификатор элемента управления для подготовки DDX и DDV.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `HWND` Подготовки DDX и DDV элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Используйте [PrepareEditCtrl](#prepareeditctrl) вместо элементах управления для редактирования, используйте эту функцию-член для других элементов управления.  
  
 Подготовка состоит из сохраняется элемент управления `HWND` в `CDataExchange` класса. Платформа использует этот дескриптор для восстановления фокус на элемент, ранее имевший фокус в случае сбоя DDX и DDV.  
  
 Средства реализации пользовательских процедур DDX и DDV следует вызвать `PrepareCtrl` для всех элементов управления без редактирования, для которых они обмен данными через DDX или проверке данных через DDV.  
  
 Дополнительные сведения о создании собственных процедур DDX и DDV см. в разделе [Технические заметки 26](../../mfc/tn026-ddx-and-ddv-routines.md). Обзор DDX и DDV см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md) и [диалоговому](../../mfc/dialog-boxes.md).  
  
##  <a name="prepareeditctrl"></a>CDataExchange::PrepareEditCtrl  
 Платформа вызывает эту функцию-член для подготовки элемента управления редактирования для обмена данными диалогового окна (DDX) и проверки (DDV).  
  
```  
HWND PrepareEditCtrl(int nIDC);
```  
  
### <a name="parameters"></a>Параметры  
 `nIDC`  
 Идентификатор элемента управления для подготовки DDX и DDV.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `HWND` Подготовки DDX и DDV элемента управления поля ввода.  
  
### <a name="remarks"></a>Примечания  
 Используйте [PrepareCtrl](#preparectrl) вместо этого для всех элементов управления без редактирования.  
  
 Подготовка состоит из следующих действий. Во-первых, `PrepareEditCtrl` содержит элемент управления `HWND` в `CDataExchange` класса. Платформа использует этот дескриптор для восстановления фокус на элемент, ранее имевший фокус в случае сбоя DDX и DDV. Во-вторых, `PrepareEditCtrl` устанавливает флаг `CDataExchange` класса, чтобы указать, что элемент управления, данные которого передаваемых или проверки является элементом управления.  
  
 Средства реализации пользовательских процедур DDX и DDV следует вызвать `PrepareEditCtrl` для все элементы управления, для которых они обмен данными через DDX или проверке данных через DDV edit.  
  
 Дополнительные сведения о создании собственных процедур DDX и DDV см. в разделе [Технические заметки 26](../../mfc/tn026-ddx-and-ddv-routines.md). Обзор DDX и DDV см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md) и [диалоговому](../../mfc/dialog-boxes.md).  
  
##  <a name="prepareolectrl"></a>CDataExchange::PrepareOleCtrl  
 Платформа вызывает эту функцию-член для подготовки указанного элемента управления OLE для обмена данными диалогового окна (DDX) и проверки (DDV).  
  
```  
COleControlSite* PrepareOleCtrl(int nIDC);
```  
  
### <a name="parameters"></a>Параметры  
 `nIDC`  
 Идентификатор элемента управления OLE для подготовки DDX и DDV.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на узел элемента управления OLE.  
  
### <a name="remarks"></a>Примечания  
 Используйте [PrepareEditCtrl](#prepareeditctrl) вместо элементах управления для редактирования или [PrepareCtrl](#preparectrl) для всех других элементов управления без OLE.  
  
 Средства реализации пользовательских процедур DDX и DDV следует вызвать `PrepareOleCtrl` для всех элементов управления OLE, для которых они обмен данными через DDX или проверке данных через DDV.  
  
 Дополнительные сведения о создании собственных процедур DDX и DDV см. в разделе [Технические заметки 26](../../mfc/tn026-ddx-and-ddv-routines.md). Обзор DDX и DDV см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md) и [диалоговому](../../mfc/dialog-boxes.md).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC приложения](../../visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange)   
 [CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata)


