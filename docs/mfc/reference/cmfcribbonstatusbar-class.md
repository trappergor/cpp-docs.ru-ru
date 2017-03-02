---
title: "Класс CMFCRibbonStatusBar | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonStatusBar
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonStatusBar class
ms.assetid: 921eb57f-3b40-49fa-a38c-3f2fb6dc2893
caps.latest.revision: 37
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
ms.openlocfilehash: 8fc2ec14c3f6320f45128bf36824ce7f9b8de9c5
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonstatusbar-class"></a>Класс CMFCRibbonStatusBar
`CMFCRibbonStatusBar` Класс реализует строки состояния, может отображать элементы ленты.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonStatusBar : public CMFCRibbonBar  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonStatusBar::AddDynamicElement](#adddynamicelement)|Добавляет динамический элемент строки состояния ленты.|  
|[CMFCRibbonStatusBar::AddElement](#addelement)|Добавляет новый элемент ленты, строка состояния ленты.|  
|[CMFCRibbonStatusBar::AddExtendedElement](#addextendedelement)|Добавляет элемент ленты в расширенной области строки состояния ленты.|  
|[CMFCRibbonStatusBar::AddSeparator](#addseparator)|Добавляет разделитель строки состояния ленты.|  
|[CMFCRibbonStatusBar::Create](#create)|Создает строку состояния ленты.|  
|[CMFCRibbonStatusBar::CreateEx](#createex)|Создает строку состояния ленты с расширенным стилем.|  
|[CMFCRibbonStatusBar::FindByID](#findbyid)||  
|[CMFCRibbonStatusBar::FindElement](#findelement)|Возвращает указатель на элемент, имеющий идентификатор указанной команды.|  
|[CMFCRibbonStatusBar::GetCount](#getcount)|Возвращает количество элементов, которые находятся в основной области строки состояния ленты.|  
|[CMFCRibbonStatusBar::GetElement](#getelement)|Возвращает указатель на элемент, расположенный по указанному индексу.|  
|[CMFCRibbonStatusBar::GetExCount](#getexcount)|Возвращает количество элементов, которые находятся в расширенной области строки состояния ленты.|  
|[CMFCRibbonStatusBar::GetExElement](#getexelement)|Возвращает указатель на элемент, расположенный по заданному индексу в расширенной области строки состояния ленты.|  
|[CMFCRibbonStatusBar::GetExtendedArea](#getextendedarea)||  
|[CMFCRibbonStatusBar::GetSpace](#getspace)||  
|[CMFCRibbonStatusBar::IsBottomFrame](#isbottomframe)||  
|[CMFCRibbonStatusBar::IsExtendedElement](#isextendedelement)||  
|[CMFCRibbonStatusBar::IsInformationMode](#isinformationmode)|Определяет, включен ли режим сведения для строки состояния ленты.|  
|[CMFCRibbonStatusBar::RecalcLayout](#recalclayout)|(Переопределяет [CMFCRibbonBar::RecalcLayout](../../mfc/reference/cmfcribbonbar-class.md#recalclayout).)|  
|[CMFCRibbonStatusBar::RemoveAll](#removeall)|Удаляет все элементы из строки состояния ленты.|  
|[CMFCRibbonStatusBar::RemoveElement](#removeelement)|Удаляет элемент с заданным Идентификатором команды в строке состояния ленты.|  
|[CMFCRibbonStatusBar::SetInformation](#setinformation)|Включает или отключает режим сведения для строки состояния ленты.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonStatusBar::OnDrawInformation](#ondrawinformation)|Отображает сведения о строке, которая появляется на строке при включении режима сведения состояния ленты.|  
  
## <a name="remarks"></a>Примечания  
 Пользователи могут изменять видимость элементов ленты в строке состояния ленты с помощью встроенных контекстное меню для строки состояния ленты. Вы можете динамически добавлять или удалять элементы.  
  
 Строки состояния ленты имеет две области: область основной и расширенной области. Расширенная область отображается справа от строки состояния ленты и отображается другим цветом, чем основной области.  
  
 Как правило основной области в строке состояния отображаются уведомления о состоянии и расширенной области отображаются элементы управления представления. Расширенная область остается видимым при условии при изменении пользователем размера строки состояния ленты.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как использовать различные методы в `CMFCRibbonStatusBar` класса. В примере показано добавление нового элемента ленты в строки состояния ленты, добавьте элемент ленты в расширенной области строки состояния ленты добавить разделители и включить обычный режим для строки состояния ленты.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#15;](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbar-class_1.cpp)]  
[!code-cpp[NVC_MFC_RibbonApp №&16;](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbar-class_2.cpp)]  
  
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
  
##  <a name="a-nameadddynamicelementa--cmfcribbonstatusbaradddynamicelement"></a><a name="adddynamicelement"></a>CMFCRibbonStatusBar::AddDynamicElement  
 Добавляет динамический элемент строки состояния ленты.  
  
```  
void AddDynamicElement(CMFCRibbonBaseElement* pElement);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pElement`  
 Указатель динамических элементов.  
  
### <a name="remarks"></a>Примечания  
 В отличие от регулярных элементов динамические элементы, не изменяются и настройка меню в строке состояния не отображаются.  
  
##  <a name="a-nameaddelementa--cmfcribbonstatusbaraddelement"></a><a name="addelement"></a>CMFCRibbonStatusBar::AddElement  
 Добавляет новый элемент ленты, строка состояния ленты.  
  
```  
void AddElement(
    CMFCRibbonBaseElement* pElement,  
    LPCTSTR lpszLabel,  
    BOOL bIsVisible=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pElement`  
 Указатель на добавленный элемент.  
  
 [in] `lpszLabel`  
 Текстовая метка элемента.  
  
 [in] `bIsVisible`  
 `TRUE`Если вы хотите добавить элемент в качестве видимой, `FALSE` Если вы хотите добавить элемент как скрытые.  
  
##  <a name="a-nameaddextendedelementa--cmfcribbonstatusbaraddextendedelement"></a><a name="addextendedelement"></a>CMFCRibbonStatusBar::AddExtendedElement  
 Добавляет элемент ленты в расширенной области строки состояния ленты.  
  
```  
void AddExtendedElement(
    CMFCRibbonBaseElement* pElement,  
    LPCTSTR lpszLabel,  
    BOOL bIsVisible=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pElement`  
 Указатель на добавленный элемент.  
  
 [in] `lpszLabel`  
 Текстовая метка элемента.  
  
 [in] `bIsVisible`  
 `TRUE`Если вы хотите добавить элемент в качестве видимой, `FALSE` Если вы хотите добавить элемент как скрытые.  
  
### <a name="remarks"></a>Примечания  
 Расширенная область находится в правой части элемента управления состоянием строки.  
  
##  <a name="a-nameaddseparatora--cmfcribbonstatusbaraddseparator"></a><a name="addseparator"></a>CMFCRibbonStatusBar::AddSeparator  
 Добавляет разделитель строки состояния ленты.  
  
```  
void AddSeparator();
```  
  
### <a name="remarks"></a>Примечания  
 Платформа служит разделителем после метода [CMFCRibbonStatusBar::AddElement](#addelement). Вставляет последнего элемента.  
  
##  <a name="a-namecreatea--cmfcribbonstatusbarcreate"></a><a name="create"></a>CMFCRibbonStatusBar::Create  
 Создает строку состояния ленты.  
  
```  
BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,  
    UINT nID=AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pParentWnd`  
 Указатель на родительское окно.  
  
 [in] `dwStyle`  
 Сочетание логического или стили элемента управления.  
  
 [in] `nID`  
 Идентификатор элемента управления строки состояния.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если в строке состояния будет создана успешно, `FALSE` в противном случае.  
  
##  <a name="a-namecreateexa--cmfcribbonstatusbarcreateex"></a><a name="createex"></a>CMFCRibbonStatusBar::CreateEx  
 Создает строку состояния ленты с расширенным стилем.  
  
```  
BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle=0,  
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,  
    UINT nID=AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentWnd`  
 Указатель на родительское окно.  
  
 `dwCtrlStyle`  
 Сочетание логического или дополнительные стили для создания объекта состояния панели.  
  
 `dwStyle`  
 Стиль элемента управления строки состояния.  
  
 `nID`  
 Идентификатор элемента управления строки состояния.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если в строке состояния будет создана успешно, `FALSE` в противном случае.  
  
##  <a name="a-namefindbyida--cmfcribbonstatusbarfindbyid"></a><a name="findbyid"></a>CMFCRibbonStatusBar::FindByID  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCRibbonBaseElement* FindByID(UINT uiCmdID, BOOL = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiCmdID`  
 [in] `BOOL`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namefindelementa--cmfcribbonstatusbarfindelement"></a><a name="findelement"></a>CMFCRibbonStatusBar::FindElement  
 Возвращает указатель на элемент, имеющий идентификатор указанной команды.  
  
```  
CMFCRibbonBaseElement* FindElement(UINT uiID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiID`  
 Идентификатор элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент, имеющий идентификатор указанной команды. `NULL`Если такого элемента не существует.  
  
##  <a name="a-namegetcounta--cmfcribbonstatusbargetcount"></a><a name="getcount"></a>CMFCRibbonStatusBar::GetCount  
 Возвращает количество элементов, которые находятся в основной области строки состояния ленты.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов, которые находятся в основной области строки состояния ленты.  
  
##  <a name="a-namegetelementa--cmfcribbonstatusbargetelement"></a><a name="getelement"></a>CMFCRibbonStatusBar::GetElement  
 Возвращает указатель на элемент, расположенный по указанному индексу.  
  
```  
CMFCRibbonBaseElement* GetElement(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Задает отсчитываемый от нуля индекс элемента, который находится в основной области строки состояния.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент, расположенный по указанному индексу. `NULL`Если индекс меньше нуля или превышает число элементов в строке состояния.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetexcounta--cmfcribbonstatusbargetexcount"></a><a name="getexcount"></a>CMFCRibbonStatusBar::GetExCount  
 Возвращает количество элементов, которые находятся в расширенной области строки состояния ленты.  
  
```  
int GetExCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов, которые находятся в расширенной области строки состояния ленты.  
  
##  <a name="a-namegetexelementa--cmfcribbonstatusbargetexelement"></a><a name="getexelement"></a>CMFCRibbonStatusBar::GetExElement  
 Возвращает указатель на элемент, расположенный по заданному индексу в расширенной области строки состояния ленты. Расширенная область находится в правой части элемента управления состоянием строки.  
  
```  
CMFCRibbonBaseElement* GetExElement(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIndex`  
 Указывает индекс с нулевым основанием элемента, размещенного в расширенной области элемента управления строкой состояния.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент, расположенный по заданному индексу в расширенной области строки состояния ленты. Значение `NULL`, если `nIndex` меньше нуля или превышает число элементов в расширенной области строки состояния ленты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetextendedareaa--cmfcribbonstatusbargetextendedarea"></a><a name="getextendedarea"></a>CMFCRibbonStatusBar::GetExtendedArea  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL GetExtendedArea(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rect`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetspacea--cmfcribbonstatusbargetspace"></a><a name="getspace"></a>CMFCRibbonStatusBar::GetSpace  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetSpace() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisbottomframea--cmfcribbonstatusbarisbottomframe"></a><a name="isbottomframe"></a>CMFCRibbonStatusBar::IsBottomFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsBottomFrame() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisextendedelementa--cmfcribbonstatusbarisextendedelement"></a><a name="isextendedelement"></a>CMFCRibbonStatusBar::IsExtendedElement  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsExtendedElement(CMFCRibbonBaseElement* pElement) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pElement`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameisinformationmodea--cmfcribbonstatusbarisinformationmode"></a><a name="isinformationmode"></a>CMFCRibbonStatusBar::IsInformationMode  
 Определяет, включен ли режим сведения для строки состояния ленты.  
  
```  
BOOL IsInformationMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если в строке состояния может работать в режиме сведения; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 В режиме сведения в строке состояния скрывает все области регулярных и отображает строку сообщения.  
  
##  <a name="a-nameondrawinformationa--cmfcribbonstatusbarondrawinformation"></a><a name="ondrawinformation"></a>CMFCRibbonStatusBar::OnDrawInformation  
 Отображается строка, которая появляется на строке при включении режима сведения состояния ленты.  
  
```  
virtual void OnDrawInformation(
    CDC* pDC,  
    CString& strInfo,  
    CRect rectInfo);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `strInfo`  
 Строка с информацией.  
  
 [in] `rectInfo`  
 Ограничивающий прямоугольник.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе, если требуется настроить внешний вид строки информации в строке состояния. Используйте [CMFCRibbonStatusBar::SetInformation](#setinformation) метод для размещения в строке состояния в режиме сведения. В этом режиме скрытие всех панелей строки состояния и отображает сведения строки, заданной параметром `strInfo`.  
  
##  <a name="a-namerecalclayouta--cmfcribbonstatusbarrecalclayout"></a><a name="recalclayout"></a>CMFCRibbonStatusBar::RecalcLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameremovealla--cmfcribbonstatusbarremoveall"></a><a name="removeall"></a>CMFCRibbonStatusBar::RemoveAll  
 Удаляет все элементы из строки состояния ленты.  
  
```  
void RemoveAll();
```  
  
##  <a name="a-nameremoveelementa--cmfcribbonstatusbarremoveelement"></a><a name="removeelement"></a>CMFCRibbonStatusBar::RemoveElement  
 Удаляет элемент с заданным Идентификатором команды в строке состояния ленты.  
  
```  
BOOL RemoveElement(UINT uiID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiID`  
 Идентификатор элемента, удаляемого из строки состояния.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если элемент с указанным `uiID` удаляется. В противном случае — значение `FALSE`.  
  
##  <a name="a-namesetinformationa--cmfcribbonstatusbarsetinformation"></a><a name="setinformation"></a>CMFCRibbonStatusBar::SetInformation  
 Включает или отключает режим сведения для строки состояния ленты.  
  
```  
void SetInformation(LPCTSTR lpszInfo);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszInfo`  
 Строка с информацией.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для размещения в строке состояния в режиме сведения. В этом режиме скрытие всех панелей строки состояния и отображает сведения строки, заданной параметром `lpszInfo`.  
  
 При lpszInfo `NULL`, в строке состояния возвращается в обычный режим.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)   
 [Класс CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [Класс CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)

