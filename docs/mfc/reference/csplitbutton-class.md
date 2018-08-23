---
title: Класс CSplitButton | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSplitButton
- AFXCMN/CSplitButton
- AFXCMN/CSplitButton::CSplitButton
- AFXCMN/CSplitButton::Create
- AFXCMN/CSplitButton::SetDropDownMenu
- AFXCMN/CSplitButton::OnDropDown
dev_langs:
- C++
helpviewer_keywords:
- CSplitButton [MFC], CSplitButton
- CSplitButton [MFC], Create
- CSplitButton [MFC], SetDropDownMenu
- CSplitButton [MFC], OnDropDown
ms.assetid: 6844d0a9-6408-4e44-9b5f-57628ed8bad6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d7fd35c351639d4b7b5f3b9dbbbce1c5e7cbcb79
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "42538931"
---
# <a name="csplitbutton-class"></a>Класс CSplitButton
`CSplitButton` Класс представляет элемент управления split button. Элемент управления "кнопка разделения" реализует поведение по умолчанию, когда пользователь щелкает основную часть кнопки, и отображает раскрывающееся меню, когда пользователь щелкает раскрывающуюся стрелку кнопки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSplitButton : public CButton  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSplitButton::CSplitButton](#csplitbutton)|Создает объект `CSplitButton`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSplitButton::Create](#create)|Создает элемент управления split button с указанными стилями и присоединяет его к текущему `CSplitButton` объекта.|  
|[CSplitButton::SetDropDownMenu](#setdropdownmenu)|Задает раскрывающемся меню, которое отображается, когда пользователь щелкает стрелку раскрывающегося списка для текущего управления SplitButton.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSplitButton::OnDropDown](#ondropdown)|Обрабатывает уведомление BCN_DROPDOWN, система отправляет, когда пользователь щелкает стрелку раскрывающегося списка для текущего управления SplitButton.|  
  
## <a name="remarks"></a>Примечания  
 `CSplitButton` Класс является производным от [CButton](../../mfc/reference/cbutton-class.md) класса. Элемент управления split button является элементом управления кнопки, стиль которого является BS_SPLITBUTTON. Пользовательское меню отображается в том случае, когда пользователь щелкает стрелку раскрывающегося списка. Дополнительные сведения см. в разделе стили BS_SPLITBUTTON и BS_DEFSPLITBUTTON [стили кнопок](http://msdn.microsoft.com/library/windows/desktop/bb775951).  
  
 На следующем рисунке представлен диалоговое окно, которое содержит элемент управления страничного навигатора и элемент управления button (1) разбиения. (2) стрелку раскрывающегося списка уже был выполнен щелчок, и отображается меню (3).  
  
 ![Диалоговое окно с элементом управления splitbutton и на пейджер. ](../../mfc/reference/media/splitbutton_pager.png "splitbutton_pager")  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CSplitButton`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
 Этот класс поддерживается в Windows Vista и более поздних версий.  
  
 Дополнительные требования для данного класса описаны в [построения требования для Windows Vista стандартные элементы управления](../../mfc/build-requirements-for-windows-vista-common-controls.md).  
  
##  <a name="create"></a>  CSplitButton::Create  
 Создает элемент управления split button с указанными стилями и присоединяет его к текущему `CSplitButton` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|[in] *dwStyle*|Побитовое сочетание (OR) стили элемента управления к элементу управления. Дополнительные сведения см. в разделе [стили кнопок](../../mfc/reference/styles-used-by-mfc.md#button-styles).|  
|[in] *rect*|Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, содержащая положение и размер элемента управления.|  
|[in] *pParentWnd*|Ненулевой указатель на [CWnd](../../mfc/reference/cwnd-class.md) объект, являющийся родительского окна элемента управления.|  
|[in] *nID*|Идентификатор элемента управления.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.  
  
##  <a name="csplitbutton"></a>  CSplitButton::CSplitButton  
 Создает объект `CSplitButton`. Параметры конструктора укажите подменю, который отображается, когда пользователь щелкает стрелку раскрывающегося списка элемента управления SplitButton.  
  
```  
CSplitButton();

 
CSplitButton(
    UINT nMenuId,   
    UINT nSubMenuId)  
CSplitButton(CMenu* pMenu)  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|[in] *nMenuId*|Идентификатор ресурса меню.|  
|[in] *nSubMenuId*|Идентификатор ресурса меню.|  
|[in] *pMenu*|Указатель на [CMenu](../../mfc/reference/cmenu-class.md) , указывающий подменю. `CSplitButton` Объекта удалений `CMenu` объекта и его связанные HMENU при `CSplitButton` объект выходит за пределы области.|  
  
### <a name="remarks"></a>Примечания  
 Используйте [CSplitButton::Create](#create) метод, чтобы создать элемент управления split button и подключить его к `CSplitButton` объекта.  
  
##  <a name="ondropdown"></a>  CSplitButton::OnDropDown  
 Обрабатывает уведомление BCN_DROPDOWN, система отправляет, когда пользователь щелкает стрелку раскрывающегося списка для текущего управления SplitButton.  
  
```  
afx_msg void OnDropDown(
    NMHDR* pNMHDR,   
    LRESULT* pResult);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|[in] *pNMHDR*|Указатель на [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) структуру, содержащую сведения о [BCN_DROPDOWN](http://msdn.microsoft.com/library/windows/desktop/bb775983) уведомлений.|  
|[out] *pResult*|(Не используется; значение не возвращается). Возвращаемое значение [BCN_DROPDOWN](http://msdn.microsoft.com/library/windows/desktop/bb775983) уведомлений.|  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь щелкает стрелку раскрывающегося списка на элемент управления split button, система отправляет уведомление BCN_DROPDOWN сообщения, в котором `OnDropDown` метод обрабатывает. Тем не менее `CSplitButton` объекта не перенаправляет уведомление BCN_DROPDOWN, чтобы элемент управления, содержащий элемент управления split button. Следовательно содержащегося элемента управления не поддерживает настраиваемое действие в ответ на уведомление.  
  
 Чтобы реализовать настраиваемое действие, которое поддерживает содержащегося элемента управления, используйте [CButton](../../mfc/reference/cbutton-class.md) объект с стиль BS_SPLITBUTTON вместо `CSplitButton` объекта. Затем Реализуйте обработчик уведомление BCN_DROPDOWN в `CButton` объекта. Дополнительные сведения см. в разделе [стили кнопок](../../mfc/reference/styles-used-by-mfc.md#button-styles).  
  
 Для реализации настраиваемого действия, что Разворачивающаяся кнопка самого элемента управления поддерживает используйте [сообщений отражения](../../mfc/tn062-message-reflection-for-windows-controls.md). Собственный производный класс от `CSplitButton` класс и назовите его, например, CMySplitButton. Затем добавьте на следующей карте сообщения приложение может обрабатывать уведомление BCN_DROPDOWN:  
  
```  
BEGIN_MESSAGE_MAP(CMySplitButton,
    CSplitButton)  
    ON_NOTIFY_REFLECT(BCN_DROPDOWN, &CMySplitButton::OnDropDown)  
END_MESSAGE_MAP()  
```  
  
##  <a name="setdropdownmenu"></a>  CSplitButton::SetDropDownMenu  
 Задает раскрывающемся меню, которое отображается, когда пользователь щелкает стрелку раскрывающегося списка для текущего управления SplitButton.  
  
```  
void SetDropDownMenu(
    UINT nMenuId,   
    UINT nSubMenuId);  
  
void SetDropDownMenu(CMenu* pMenu);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|[in] *nMenuId*|Идентификатор ресурса меню.|  
|[in] *nSubMenuId*|Идентификатор ресурса меню.|  
|[in] *pMenu*|Указатель на [CMenu](../../mfc/reference/cmenu-class.md) , указывающий подменю. `CSplitButton` Объекта удалений `CMenu` объекта и его связанные HMENU при `CSplitButton` объект выходит за пределы области.|  
  
### <a name="remarks"></a>Примечания  
 *NMenuId* параметр определяет строку меню, который является горизонтальный список элементов строки меню. *NSubMenuId* параметр является отсчитываемый от нуля индекс число, идентифицирующее подменю, который является списком раскрывающегося списка пунктов меню, связанные с каждым пунктом меню панели. Например типичное приложение имеет меню, которое содержит элементы панели меню «Файл», «Изменить» и «Справка». Элемент панели меню «Файл» есть вложенное меню с элементами меню «Открыть», «Закрыть» и «Exit». Если при нажатии стрелки раскрывающегося списка элемента управления split button, элемент управления отображает меню не в строке меню.  
  
 На следующем рисунке представлен диалоговое окно, которое содержит элемент управления страничного навигатора и элемент управления button (1) разбиения. (2) стрелку раскрывающегося списка уже был выполнен щелчок, и отображается меню (3).  
  
 ![Диалоговое окно с элементом управления splitbutton и на пейджер. ](../../mfc/reference/media/splitbutton_pager.png "splitbutton_pager")  
  
### <a name="example"></a>Пример  
 Первый оператор в следующем примере кода демонстрируется [CSplitButton::SetDropDownMenu](#setdropdownmenu) метод. Мы создали меню с помощью ресурсов Visual Studio редактор, который автоматически присваивается имя идентификатора панели меню, IDR_MENU1. *NSubMenuId* параметр, который равен нулю, ссылается на единственный вложенного меню в строке меню.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/csplitbutton-class_1.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Класс CSplitButton](../../mfc/reference/csplitbutton-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CButton](../../mfc/reference/cbutton-class.md)
