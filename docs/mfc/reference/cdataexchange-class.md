---
title: CDataExchange-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CDataExchange [MFC], CDataExchange
- CDataExchange [MFC], Fail
- CDataExchange [MFC], PrepareCtrl
- CDataExchange [MFC], PrepareEditCtrl
- CDataExchange [MFC], PrepareOleCtrl
- CDataExchange [MFC], m_bSaveAndValidate
- CDataExchange [MFC], m_pDlgWnd
ms.assetid: 84ed6113-325d-493e-a75d-223f03a992b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2ed2f918a51c1dca1aa7e1713ac919102a599e38
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953351"
---
# <a name="cdataexchange-class"></a>CDataExchange-класс
Поддерживает процедуры обмена данными диалогового окна (DDX) и проверки данных диалогового окна (DDV), используемые классами Microsoft Foundation.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDataExchange  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDataExchange::CDataExchange](#cdataexchange)|Создает объект `CDataExchange`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDataExchange::Fail](#fail)|Вызывается при сбое проверки. Сбрасывает фокуса к предыдущему элементу управления и вызывает исключение.|  
|[CDataExchange::PrepareCtrl](#preparectrl)|Подготавливает заданный элемент управления для обмена данными или проверки. Использование элементов управления nonedit.|  
|[CDataExchange::PrepareEditCtrl](#prepareeditctrl)|Подготавливает редактирования элемента управления для обмена данными или проверки.|  
|[CDataExchange::PrepareOleCtrl](#prepareolectrl)|Подготавливает заданный элемент управления OLE для обмена данными или проверки. Использование элементов управления nonedit.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDataExchange::m_bSaveAndValidate](#m_bsaveandvalidate)|Флаг, указывающий направление DDX и DDV.|  
|[CDataExchange::m_pDlgWnd](#m_pdlgwnd)|Диалоговое окно или окно, где обмена данными выполняется.|  
  
## <a name="remarks"></a>Примечания  
 `CDataExchange` не имеет базового класса.  
  
 Этот класс используется при создании процедуры обмена данными для пользовательских типов данных или элементов управления, или при создании собственных процедур проверки данных. Дополнительные сведения о написании собственных процедур DDX и DDV см. в разделе [Технические заметки 26](../../mfc/tn026-ddx-and-ddv-routines.md). Обзор DDX и DDV см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md) и [диалоговым окнам](../../mfc/dialog-boxes.md).  
  
 Объект `CDataExchange` объект предоставляет контекстные сведения, необходимые для размещения DDX и DDV вступили в. Флаг *m_bSaveAndValidate* — **FALSE** при использовании DDX для заполнения начального значения элементов управления диалогового окна из элементов данных. Флаг *m_bSaveAndValidate* — **TRUE** при использовании DDX для набора текущие значения элементов управления диалоговых окон в данные-члены и когда DDV используется для проверки значений данных. DDV проверка завершается неудачно, процедура DDV отобразит сообщение, описывающее ошибок на входе. Затем вызывается процедура DDV `Fail` Сброс фокус на элемент управления, вызвавший ошибку и выдается исключение для остановки процесса проверки.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CDataExchange`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="cdataexchange"></a>  CDataExchange::CDataExchange  
 Вызовите эту функцию-член для создания `CDataExchange` объекта.  
  
```  
CDataExchange(
    CWnd* pDlgWnd,  
    BOOL bSaveAndValidate);
```  
  
### <a name="parameters"></a>Параметры  
 *pDlgWnd*  
 Указатель на родительское окно, которое содержит элемент управления. Обычно это [CDialog](../../mfc/reference/cdialog-class.md)-производного объекта.  
  
 *bSaveAndValidate*  
 Если **TRUE**, этот объект для проверки данных, а затем записывает данные из элементов управления к членам. Если **FALSE**, будет перемещен этот объект данных от членов для элементов управления.  
  
### <a name="remarks"></a>Примечания  
 Создать `CDataExchange` объекта самостоятельно для хранения дополнительных сведений в объекте данных exchange для вашего окна передачи [CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange) функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCControlLadenDialog#70](../../mfc/codesnippet/cpp/cdataexchange-class_1.cpp)]  
  
##  <a name="fail"></a>  CDataExchange::Fail  
 Платформа вызывает эту функцию-член, при сбое операции проверки (DDV) данных диалогового окна.  
  
```  
void Fail();
```  
  
### <a name="remarks"></a>Примечания  
 `Fail` Восстанавливает фокуса и выделения для элемента управления, сбой которого проверки (если имеется элемент управления для восстановления). `Fail` затем вызывает исключение типа [CUserException](../../mfc/reference/cuserexception-class.md) для остановки процесса проверки. Исключение вызывает сообщение, описывающее ошибку для отображения. После проверки DDV произойдет сбой, пользователь может повторно войти данных в элементе управления, вызвавший ошибку.  
  
 Можно вызвать средства реализации пользовательских процедур DDV `Fail` из своих программах при сбое проверки.  
  
 Дополнительные сведения о написании собственных процедур DDX и DDV см. в разделе [Технические заметки 26](../../mfc/tn026-ddx-and-ddv-routines.md). Обзор DDX и DDV см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md) и [диалоговому](../../mfc/dialog-boxes.md).  
  
##  <a name="m_bsaveandvalidate"></a>  CDataExchange::m_bSaveAndValidate  
 Этот флаг указывает направление операции с данными exchange (DDX) диалогового окна.  
  
```  
BOOL m_bSaveAndValidate;  
```  
  
### <a name="remarks"></a>Примечания  
 Флаг ненулевое значение, если `CDataExchange` объект используется для перемещения данных из элементов управления диалоговых окон на данные-члены класса диалогового окна после пользователь редактирует элементов управления. Флаг равен нулю, если объект используется для инициализации диалогового окна элементы управления из членов данных класса диалогового окна.  
  
 Флаг также имеет ненулевое значение во время проверки данных диалогового окна (DDV).  
  
 Дополнительные сведения о написании собственных процедур DDX и DDV см. в разделе [Технические заметки 26](../../mfc/tn026-ddx-and-ddv-routines.md). Обзор DDX и DDV см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md) и [диалоговому](../../mfc/dialog-boxes.md).  
  
##  <a name="m_pdlgwnd"></a>  CDataExchange::m_pDlgWnd  
 Содержит указатель на [CWnd](../../mfc/reference/cwnd-class.md) объекта, для какой диалог обмен данными (диалоговых окон DDX) или проверки (DDV) выполняется.  
  
```  
CWnd* m_pDlgWnd;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот объект обычно является [CDialog](../../mfc/reference/cdialog-class.md) объекта. Для получения доступа к диалоговое окно, которое содержит элементы управления, они работают на пользовательские процедуры DDX и DDV средства реализации можно использовать этот указатель.  
  
 Дополнительные сведения о написании собственных процедур DDX и DDV см. в разделе [Технические заметки 26](../../mfc/tn026-ddx-and-ddv-routines.md). Обзор DDX и DDV см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md) и [диалоговому](../../mfc/dialog-boxes.md).  
  
##  <a name="preparectrl"></a>  CDataExchange::PrepareCtrl  
 Платформа вызывает эту функцию-член для подготовки указанного элемента управления для обмена данными диалогового окна (DDX) и проверки (DDV).  
  
```  
HWND PrepareCtrl(int nIDC);
```  
  
### <a name="parameters"></a>Параметры  
 *nIDC*  
 Идентификатор элемента управления для подготовки DDX и DDV.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `HWND` DDX и DDV подготовки элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Используйте [PrepareEditCtrl](#prepareeditctrl) вместо элементах управления для редактирования; используйте эту функцию-член для других элементов управления.  
  
 Подготовка состоит из элемента управления хранения `HWND` в `CDataExchange` класса. Платформа использует этот дескриптор для восстановления фокус на элемент, ранее имевший фокус в случае сбоя DDX и DDV.  
  
 Пользовательские процедуры DDX и DDV средства реализации должны вызывать `PrepareCtrl` для всех элементов управления без редактирования, для которых они обмен данными через DDX или проверки данных с помощью DDV.  
  
 Дополнительные сведения о написании собственных процедур DDX и DDV см. в разделе [Технические заметки 26](../../mfc/tn026-ddx-and-ddv-routines.md). Обзор DDX и DDV см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md) и [диалоговому](../../mfc/dialog-boxes.md).  
  
##  <a name="prepareeditctrl"></a>  CDataExchange::PrepareEditCtrl  
 Платформа вызывает эту функцию-член для подготовки элемента управления редактирования для обмена данными диалогового окна (DDX) и проверки (DDV).  
  
```  
HWND PrepareEditCtrl(int nIDC);
```  
  
### <a name="parameters"></a>Параметры  
 *nIDC*  
 Идентификатор элемента управления для подготовки DDX и DDV.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `HWND` DDX и DDV подготовки элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Используйте [PrepareCtrl](#preparectrl) вместо этого для всех элементов управления без редактирования.  
  
 Подготовка состоит из следующих действий. Во-первых, `PrepareEditCtrl` содержит элемент управления `HWND` в `CDataExchange` класса. Платформа использует этот дескриптор для восстановления фокус на элемент, ранее имевший фокус в случае сбоя DDX и DDV. Во-вторых, `PrepareEditCtrl` устанавливает флаг в `CDataExchange` класса, чтобы указать, что элемент управления, данные которого обмена или проверить является элементом управления.  
  
 Пользовательские процедуры DDX и DDV средства реализации должны вызывать `PrepareEditCtrl` для все элементы управления, для которых они обмен данными через DDX или проверки данных с помощью DDV редактирования.  
  
 Дополнительные сведения о написании собственных процедур DDX и DDV см. в разделе [Технические заметки 26](../../mfc/tn026-ddx-and-ddv-routines.md). Обзор DDX и DDV см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md) и [диалоговому](../../mfc/dialog-boxes.md).  
  
##  <a name="prepareolectrl"></a>  CDataExchange::PrepareOleCtrl  
 Платформа вызывает эту функцию-член для подготовки указанного элемента управления OLE для обмена данными диалогового окна (DDX) и проверки (DDV).  
  
```  
COleControlSite* PrepareOleCtrl(int nIDC);
```  
  
### <a name="parameters"></a>Параметры  
 *nIDC*  
 Идентификатор элемента управления OLE для подготовки DDX и DDV.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на узел элемента управления OLE.  
  
### <a name="remarks"></a>Примечания  
 Используйте [PrepareEditCtrl](#prepareeditctrl) вместо элементах управления для редактирования или [PrepareCtrl](#preparectrl) для всех других элементов управления не OLE.  
  
 Пользовательские процедуры DDX и DDV средства реализации должны вызывать `PrepareOleCtrl` для всех элементов управления OLE, для которых они обмен данными через DDX или проверки данных с помощью DDV.  
  
 Дополнительные сведения о написании собственных процедур DDX и DDV см. в разделе [Технические заметки 26](../../mfc/tn026-ddx-and-ddv-routines.md). Обзор DDX и DDV см. в разделе [обмен данными диалоговых окон и проверка](../../mfc/dialog-data-exchange-and-validation.md) и [диалоговому](../../mfc/dialog-boxes.md).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC: VIEWEX](../../visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange)   
 [CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata)

