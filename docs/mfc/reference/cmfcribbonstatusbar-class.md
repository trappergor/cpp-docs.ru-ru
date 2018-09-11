---
title: Класс CMFCRibbonStatusBar | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonStatusBar
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddDynamicElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddExtendedElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddSeparator
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::Create
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::CreateEx
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::FindByID
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::FindElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetCount
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExCount
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExtendedArea
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetSpace
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsBottomFrame
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsExtendedElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsInformationMode
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RecalcLayout
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RemoveAll
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RemoveElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::SetInformation
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::OnDrawInformation
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonStatusBar [MFC], AddDynamicElement
- CMFCRibbonStatusBar [MFC], AddElement
- CMFCRibbonStatusBar [MFC], AddExtendedElement
- CMFCRibbonStatusBar [MFC], AddSeparator
- CMFCRibbonStatusBar [MFC], Create
- CMFCRibbonStatusBar [MFC], CreateEx
- CMFCRibbonStatusBar [MFC], FindByID
- CMFCRibbonStatusBar [MFC], FindElement
- CMFCRibbonStatusBar [MFC], GetCount
- CMFCRibbonStatusBar [MFC], GetElement
- CMFCRibbonStatusBar [MFC], GetExCount
- CMFCRibbonStatusBar [MFC], GetExElement
- CMFCRibbonStatusBar [MFC], GetExtendedArea
- CMFCRibbonStatusBar [MFC], GetSpace
- CMFCRibbonStatusBar [MFC], IsBottomFrame
- CMFCRibbonStatusBar [MFC], IsExtendedElement
- CMFCRibbonStatusBar [MFC], IsInformationMode
- CMFCRibbonStatusBar [MFC], RecalcLayout
- CMFCRibbonStatusBar [MFC], RemoveAll
- CMFCRibbonStatusBar [MFC], RemoveElement
- CMFCRibbonStatusBar [MFC], SetInformation
- CMFCRibbonStatusBar [MFC], OnDrawInformation
ms.assetid: 921eb57f-3b40-49fa-a38c-3f2fb6dc2893
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 378ecc3c02a78bc99fa999090119e75a45dc27a7
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "42540297"
---
# <a name="cmfcribbonstatusbar-class"></a>Класс CMFCRibbonStatusBar
`CMFCRibbonStatusBar` Класс реализует элемент управления строки состояния, которая может отображать элементы ленты.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonStatusBar : public CMFCRibbonBar  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCRibbonStatusBar::AddDynamicElement](#adddynamicelement)|Добавляет элемент динамические строки состояния ленты.|  
|[CMFCRibbonStatusBar::AddElement](#addelement)|Добавляет новый элемент ленты для строки состояния ленты.|  
|[CMFCRibbonStatusBar::AddExtendedElement](#addextendedelement)|Добавляет элемент ленты в расширенной области строки состояния ленты.|  
|[CMFCRibbonStatusBar::AddSeparator](#addseparator)|Добавляет разделитель строки состояния ленты.|  
|[CMFCRibbonStatusBar::Create](#create)|Создает строку статуса ленты.|  
|[CMFCRibbonStatusBar::CreateEx](#createex)|Создает строку статуса ленты с расширенным стилем.|  
|[CMFCRibbonStatusBar::FindByID](#findbyid)||  
|[CMFCRibbonStatusBar::FindElement](#findelement)|Возвращает указатель на элемент с указанным идентификатором команды.|  
|[CMFCRibbonStatusBar::GetCount](#getcount)|Возвращает количество элементов, расположенных в основной области строки состояния ленты.|  
|[CMFCRibbonStatusBar::GetElement](#getelement)|Возвращает указатель на элемент, расположенный по указанному индексу.|  
|[CMFCRibbonStatusBar::GetExCount](#getexcount)|Возвращает количество элементов, расположенных в расширенной области строки состояния ленты.|  
|[CMFCRibbonStatusBar::GetExElement](#getexelement)|Возвращает указатель на элемент, расположенный по заданному индексу в расширенной области строки состояния ленты.|  
|[CMFCRibbonStatusBar::GetExtendedArea](#getextendedarea)||  
|[CMFCRibbonStatusBar::GetSpace](#getspace)||  
|[CMFCRibbonStatusBar::IsBottomFrame](#isbottomframe)||  
|[CMFCRibbonStatusBar::IsExtendedElement](#isextendedelement)||  
|[CMFCRibbonStatusBar::IsInformationMode](#isinformationmode)|Определяет, включен ли режим сведения для строки состояния ленты.|  
|[CMFCRibbonStatusBar::RecalcLayout](#recalclayout)|(Переопределяет [CMFCRibbonBar::RecalcLayout](../../mfc/reference/cmfcribbonbar-class.md#recalclayout).)|  
|[CMFCRibbonStatusBar::RemoveAll](#removeall)|Удаляет все элементы из строки состояния ленты.|  
|[CMFCRibbonStatusBar::RemoveElement](#removeelement)|Удаляет элемент, имеющий заданный идентификатор команды из строки состояния ленты.|  
|[CMFCRibbonStatusBar::SetInformation](#setinformation)|Включает или отключает режим сведения для строки состояния ленты.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCRibbonStatusBar::OnDrawInformation](#ondrawinformation)|Отображает сведения строка, которая появляется на строке при включении режима сведения состояния ленты.|  
  
## <a name="remarks"></a>Примечания  
 Пользователи могут изменять видимость элементов ленты в строку статуса ленты с помощью встроенных контекстное меню для строки состояния ленты. Вы можете динамически добавлять или удалять элементы.  
  
 Строки состояния ленты содержит две области: область основного и расширенные области. Расширенной области отображается в правой части строки состояния ленты и отображается другим цветом, чем основную область.  
  
 Как правило в основной области строки состояния отображаются уведомления о состоянии и в расширенной области отображаются элементы управления представления. При изменении пользователем размера строки состояния ленты расширенной области максимально долго остается видимым.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует использование различных методов `CMFCRibbonStatusBar` класса. В примере показано добавление нового элемента ленты в строки состояния ленты, добавьте элемент ленты в расширенной области строки состояния ленты, добавить разделитель и включить обычный режим для строки состояния ленты.  
  
 [!code-cpp[NVC_MFC_RibbonApp#15](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbar-class_1.cpp)]  
[!code-cpp[NVC_MFC_RibbonApp#16](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)  
  
 [CMFCRibbonStatusBar](../../mfc/reference/cmfcribbonstatusbar-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxribbonstatusbar.h  
  
##  <a name="adddynamicelement"></a>  CMFCRibbonStatusBar::AddDynamicElement  
 Добавляет элемент динамические строки состояния ленты.  
  
```  
void AddDynamicElement(CMFCRibbonBaseElement* pElement);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pElement*  
 Указатель на динамический элемент.  
  
### <a name="remarks"></a>Примечания  
 В отличие от регулярных элементов динамические элементы, не изменяются, и в меню "Настройка" в строке состояния не отображаются.  
  
##  <a name="addelement"></a>  CMFCRibbonStatusBar::AddElement  
 Добавляет новый элемент ленты для строки состояния ленты.  
  
```  
void AddElement(
    CMFCRibbonBaseElement* pElement,  
    LPCTSTR lpszLabel,  
    BOOL bIsVisible=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pElement*  
 Указатель на добавленный элемент.  
  
 [in] *lpszLabel*  
 Текстовая метка элемента.  
  
 [in] *bIsVisible*  
 Значение TRUE, если вы хотите добавьте элемент как видимый, FALSE, если вы хотите добавить элемент как скрытые.  
  
##  <a name="addextendedelement"></a>  CMFCRibbonStatusBar::AddExtendedElement  
 Добавляет элемент ленты в расширенной области строки состояния ленты.  
  
```  
void AddExtendedElement(
    CMFCRibbonBaseElement* pElement,  
    LPCTSTR lpszLabel,  
    BOOL bIsVisible=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pElement*  
 Указатель на добавленный элемент.  
  
 [in] *lpszLabel*  
 Текстовая метка элемента.  
  
 [in] *bIsVisible*  
 Значение TRUE, если вы хотите добавьте элемент как видимый, FALSE, если вы хотите добавить элемент как скрытые.  
  
### <a name="remarks"></a>Примечания  
 Расширенная область находится в правой части элемента управления состоянием строки.  
  
##  <a name="addseparator"></a>  CMFCRibbonStatusBar::AddSeparator  
 Добавляет разделитель строки состояния ленты.  
  
```  
void AddSeparator();
```  
  
### <a name="remarks"></a>Примечания  
 Платформа добавляет разделитель после метода [CMFCRibbonStatusBar::AddElement](#addelement). Вставляет последнего элемента.  
  
##  <a name="create"></a>  CMFCRibbonStatusBar::Create  
 Создает строку статуса ленты.  
  
```  
BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,  
    UINT nID=AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pParentWnd*  
 Указатель на родительское окно.  
  
 [in] *dwStyle*  
 Сочетание логического или стили элемента управления.  
  
 [in] *nID*  
 Идентификатор элемента управления строки состояния.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если в строке состояния успешно создан, значение FALSE в противном случае.  
  
##  <a name="createex"></a>  CMFCRibbonStatusBar::CreateEx  
 Создает строку статуса ленты с расширенным стилем.  
  
```  
BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle=0,  
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,  
    UINT nID=AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Параметры  
 *pParentWnd*  
 Указатель на родительское окно.  
  
 *dwCtrlStyle*  
 Сочетание логического или дополнительные стили для создания объекта строки состояния.  
  
 *dwStyle*  
 Стиль элемента управления строки состояния.  
  
 *nID*  
 Идентификатор элемента управления строки состояния.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если в строке состояния успешно создан, значение FALSE в противном случае.  
  
##  <a name="findbyid"></a>  CMFCRibbonStatusBar::FindByID  
 Для получения дополнительных сведений см. в разделе исходном коде, расположенном в **VC\\atlmfc\\src\\mfc** папке установки Visual Studio.  
  
```  
CMFCRibbonBaseElement* FindByID(UINT uiCmdID, BOOL = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *uiCmdID*  
 [in] *BOOL*  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="findelement"></a>  CMFCRibbonStatusBar::FindElement  
 Возвращает указатель на элемент с указанным идентификатором команды.  
  
```  
CMFCRibbonBaseElement* FindElement(UINT uiID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *uiID*  
 Идентификатор элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент с указанным идентификатором команды. Значение NULL, если такой элемент отсутствует.  
  
##  <a name="getcount"></a>  CMFCRibbonStatusBar::GetCount  
 Возвращает количество элементов, расположенных в основной области строки состояния ленты.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов, которые находятся в основной области строки состояния ленты.  
  
##  <a name="getelement"></a>  CMFCRibbonStatusBar::GetElement  
 Возвращает указатель на элемент, расположенный по указанному индексу.  
  
```  
CMFCRibbonBaseElement* GetElement(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nIndex*  
 Указывает отсчитываемый от нуля индекс элемента, который находится в основной области строки состояния.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент, расположенный по указанному индексу. Значение NULL, если индекс меньше нуля или превышает число элементов в строке состояния.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getexcount"></a>  CMFCRibbonStatusBar::GetExCount  
 Возвращает количество элементов, расположенных в расширенной области строки состояния ленты.  
  
```  
int GetExCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов, которые находятся в расширенной области строки состояния ленты.  
  
##  <a name="getexelement"></a>  CMFCRibbonStatusBar::GetExElement  
 Возвращает указатель на элемент, расположенный по заданному индексу в расширенной области строки состояния ленты. Расширенная область находится в правой части элемента управления состоянием строки.  
  
```  
CMFCRibbonBaseElement* GetExElement(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *nIndex*  
 Указывает индекс с нулевым основанием элемента, размещенного в расширенной области элемента управления строкой состояния.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент, расположенный по заданному индексу в расширенной области строки состояния ленты. Значение NULL, если *nIndex* является отрицательным или превышает число элементов в расширенной области строки состояния ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getextendedarea"></a>  CMFCRibbonStatusBar::GetExtendedArea  
 Для получения дополнительных сведений см. в разделе исходном коде, расположенном в **VC\\atlmfc\\src\\mfc** папке установки Visual Studio.  
  
```  
virtual BOOL GetExtendedArea(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *rect*  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getspace"></a>  CMFCRibbonStatusBar::GetSpace  
 Для получения дополнительных сведений см. в разделе исходном коде, расположенном в **VC\\atlmfc\\src\\mfc** папке установки Visual Studio.  
  
```  
int GetSpace() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isbottomframe"></a>  CMFCRibbonStatusBar::IsBottomFrame  
 Для получения дополнительных сведений см. в разделе исходном коде, расположенном в **VC\\atlmfc\\src\\mfc** папке установки Visual Studio.  
  
```  
BOOL IsBottomFrame() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isextendedelement"></a>  CMFCRibbonStatusBar::IsExtendedElement  
 Для получения дополнительных сведений см. в разделе исходном коде, расположенном в **VC\\atlmfc\\src\\mfc** папке установки Visual Studio.  
  
```  
BOOL IsExtendedElement(CMFCRibbonBaseElement* pElement) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] *pElement*  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isinformationmode"></a>  CMFCRibbonStatusBar::IsInformationMode  
 Определяет, включен ли режим сведения для строки состояния ленты.  
  
```  
BOOL IsInformationMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если в строке состояния может работать в режиме сведения; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 В режиме сведения о строке состояния скрывает все области регулярных и отображает строку сообщения.  
  
##  <a name="ondrawinformation"></a>  CMFCRibbonStatusBar::OnDrawInformation  
 Отображает строку, которая появится на строке при включении режима сведения состояния ленты.  
  
```  
virtual void OnDrawInformation(
    CDC* pDC,  
    CString& strInfo,  
    CRect rectInfo);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *основного контроллера домена*  
 Указатель на контекст устройства.  
  
 [in] *strInfo*  
 Строка с информацией.  
  
 [in] *rectInfo*  
 Ограничивающий прямоугольник.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, если вы хотите настроить внешний вид строка с информацией в строке состояния. Используйте [CMFCRibbonStatusBar::SetInformation](#setinformation) метод для размещения в строке состояния в режиме сведения. В этом режиме скрывает все панели строки состояния и отображает сведения строкой, указанной параметром *strInfo*.  
  
##  <a name="recalclayout"></a>  CMFCRibbonStatusBar::RecalcLayout  
 Для получения дополнительных сведений см. в разделе исходном коде, расположенном в **VC\\atlmfc\\src\\mfc** папке установки Visual Studio.  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="removeall"></a>  CMFCRibbonStatusBar::RemoveAll  
 Удаляет все элементы из строки состояния ленты.  
  
```  
void RemoveAll();
```  
  
##  <a name="removeelement"></a>  CMFCRibbonStatusBar::RemoveElement  
 Удаляет элемент, имеющий заданный идентификатор команды из строки состояния ленты.  
  
```  
BOOL RemoveElement(UINT uiID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *uiID*  
 Идентификатор элемента для удаления из строки состояния.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если элемент с указанным *uiID* удаляется. Значение FALSE в противном случае.  
  
##  <a name="setinformation"></a>  CMFCRibbonStatusBar::SetInformation  
 Включает или отключает режим сведения для строки состояния ленты.  
  
```  
void SetInformation(LPCTSTR lpszInfo);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *lpszInfo*  
 Строка с информацией.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно используйте для размещения в строке состояния в режиме сведения. В этом режиме скрывает все панели строки состояния и отображает сведения строкой, указанной параметром *lpszInfo*.  
  
 Когда lpszInfo имеет значение NULL, в строке состояния возвращается в обычный режим.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)   
 [Класс CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [Класс CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)
