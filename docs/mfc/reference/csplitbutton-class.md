---
title: "Класс CSplitButton | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CSplitButton class
ms.assetid: 6844d0a9-6408-4e44-9b5f-57628ed8bad6
caps.latest.revision: 24
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
ms.openlocfilehash: b4c038a177d5c501d4baad8eaa208af0e76ce231
ms.lasthandoff: 02/24/2017

---
# <a name="csplitbutton-class"></a>Класс CSplitButton
`CSplitButton` Класс представляет элемент управления split button. Элемент управления "кнопка разделения" реализует поведение по умолчанию, когда пользователь щелкает основную часть кнопки, и отображает раскрывающееся меню, когда пользователь щелкает раскрывающуюся стрелку кнопки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSplitButton : public CButton  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSplitButton::CSplitButton](#csplitbutton)|Создает объект `CSplitButton`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSplitButton::Create](#create)|Создает элемент управления split button с указанным стилем и присоединяет его к текущему `CSplitButton` объекта.|  
|[CSplitButton::SetDropDownMenu](#setdropdownmenu)|Задает раскрывающегося меню, которое отображается, когда пользователь щелкает стрелку раскрывающегося списка для текущего управления SplitButton.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSplitButton::OnDropDown](#ondropdown)|Обрабатывает `BCN_DROPDOWN` уведомление, система отправляет, когда пользователь щелкает стрелку раскрывающегося списка для текущего управления SplitButton.|  
  
## <a name="remarks"></a>Примечания  
 `CSplitButton` Класс является производным от [CButton](../../mfc/reference/cbutton-class.md) класса. Элемент управления split button является элементом управления кнопки, стиль `BS_SPLITBUTTON`. Настраиваемое меню отображается при щелчке стрелки раскрывающегося списка. Дополнительные сведения см. в разделе `BS_SPLITBUTTON` и `BS_DEFSPLITBUTTON` стили [стили кнопок](http://msdn.microsoft.com/library/windows/desktop/bb775951).  
  
 На следующем рисунке показано диалоговое окно содержит элемент управления страничного навигатора и элемент управления SplitButton (1). (2) стрелку раскрывающегося списка уже был выбран, и отображается подменю (3).  
  
 ![Диалоговое окно с элементом управления splitbutton и на пейджер. ] (../../mfc/reference/media/splitbutton_pager.png "splitbutton_pager")  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CSplitButton`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
 Этот класс поддерживается в [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] и более поздних версий.  
  
 Дополнительные требования к этому классу, описаны в [построения требования для Windows Vista Общие элементы управления](../../mfc/build-requirements-for-windows-vista-common-controls.md).  
  
##  <a name="a-namecreatea--csplitbuttoncreate"></a><a name="create"></a>CSplitButton::Create  
 Создает элемент управления split button с указанным стилем и присоединяет его к текущему `CSplitButton` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `dwStyle`|Побитовое сочетание (или) стилей применяется к элементу управления. Дополнительные сведения см. в разделе [стили кнопок](../../mfc/reference/button-styles.md).|  
|[in] `rect`|Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, содержащая положение и размер элемента управления.|  
|[in] `pParentWnd`|Ненулевой указатель [CWnd](../../mfc/reference/cwnd-class.md) объекта, родительского окна элемента управления.|  
|[in] `nID`|Идентификатор элемента управления.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае — `false`.  
  
##  <a name="a-namecsplitbuttona--csplitbuttoncsplitbutton"></a><a name="csplitbutton"></a>CSplitButton::CSplitButton  
 Создает объект `CSplitButton`. Параметры конструктора укажите подменю, которое отображается, когда пользователь щелкает стрелку раскрывающегося списка элемент управления split button.  
  
```  
CSplitButton();

 
CSplitButton(
    UINT nMenuId,   
    UINT nSubMenuId)  
CSplitButton(CMenu* pMenu)  
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `nMenuId`|Идентификатор ресурса в строке меню.|  
|[in] `nSubMenuId`|Идентификатор ресурса для подменю.|  
|[in] `pMenu`|Указатель на [CMenu](../../mfc/reference/cmenu-class.md) , указывающий подменю. `CSplitButton` Удаления объекта `CMenu` объекта и связанный с ним `HMENU` при `CSplitButton` объект выходит за пределы области.|  
  
### <a name="remarks"></a>Примечания  
 Используйте [CSplitButton::Create](#create) метод, чтобы создать элемент управления split button и присоединить его к `CSplitButton` объекта.  
  
##  <a name="a-nameondropdowna--csplitbuttonondropdown"></a><a name="ondropdown"></a>CSplitButton::OnDropDown  
 Обрабатывает `BCN_DROPDOWN` уведомление, система отправляет, когда пользователь щелкает стрелку раскрывающегося списка для текущего управления SplitButton.  
  
```  
afx_msg void OnDropDown(
    NMHDR* pNMHDR,   
    LRESULT* pResult);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `pNMHDR`|Указатель на [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) структуру, содержащую сведения о [BCN_DROPDOWN](http://msdn.microsoft.com/library/windows/desktop/bb775983) уведомления.|  
|[выходной] `pResult`|(Не используется, не имеет значения.) Возвращаемое значение [BCN_DROPDOWN](http://msdn.microsoft.com/library/windows/desktop/bb775983) уведомления.|  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь щелкает стрелку раскрывающегося списка на элемент управления split button, система отправляет `BCN_DROPDOWN` уведомлений сообщение, в котором `OnDropDown` метод обрабатывает. Тем не менее `CSplitButton` объекта не пересылать `BCN_DROPDOWN` уведомление, чтобы элемент управления, содержащий элемент управления split button. Следовательно содержащего элемента управления не поддерживает пользовательские действия в ответ на уведомление.  
  
 Чтобы реализовать настраиваемое действие, которое поддерживает контейнерный элемент управления, используйте [CButton](../../mfc/reference/cbutton-class.md) объект со стилем `BS_SPLITBUTTON` вместо `CSplitButton` объекта. Затем Реализуйте обработчик `BCN_DROPDOWN` уведомления в `CButton` объекта. Дополнительные сведения см. в разделе [стили кнопок](../../mfc/reference/button-styles.md).  
  
 Чтобы реализовать пользовательское действие, что Разворачивающаяся кнопка самого элемента управления поддерживает, используйте [сообщений отражения](../../mfc/tn062-message-reflection-for-windows-controls.md). Создать собственный производный класс от `CSplitButton` класс и назовите его, например, CMySplitButton. Затем добавьте следующие сопоставления сообщений в приложение для обработки `BCN_DROPDOWN` уведомления:  
  
```  
BEGIN_MESSAGE_MAP(CMySplitButton,
    CSplitButton)  
    ON_NOTIFY_REFLECT(BCN_DROPDOWN, &CMySplitButton::OnDropDown)  
END_MESSAGE_MAP()  
```  
  
##  <a name="a-namesetdropdownmenua--csplitbuttonsetdropdownmenu"></a><a name="setdropdownmenu"></a>CSplitButton::SetDropDownMenu  
 Задает раскрывающегося меню, которое отображается, когда пользователь щелкает стрелку раскрывающегося списка для текущего управления SplitButton.  
  
```  
void SetDropDownMenu(
    UINT nMenuId,   
    UINT nSubMenuId);  
  
void SetDropDownMenu(CMenu* pMenu);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `nMenuId`|Идентификатор ресурса в строке меню.|  
|[in] `nSubMenuId`|Идентификатор ресурса для подменю.|  
|[in] `pMenu`|Указатель на [CMenu](../../mfc/reference/cmenu-class.md) , указывающий подменю. `CSplitButton` Удаления объекта `CMenu` объекта и связанный с ним `HMENU` при `CSplitButton` объект выходит за пределы области.|  
  
### <a name="remarks"></a>Примечания  
 `nMenuId` Параметр указывает строка меню, который представляет горизонтальный список элементов меню. `nSubMenuId` Параметр является отсчитываемый от нуля индекс число, идентифицирующее вложенного меню в списке пунктов меню, связанного с каждым элементом строки меню. Например типичное приложение имеет меню, содержащего элементы панели меню «Файл», «Изменить» и «Справка». Элемент панели меню «Файл» имеет подменю, содержащее пункты меню «Открыть», «Закрыть» и «Exit». Если щелкнуть стрелку раскрывающегося списка элемент управления split button, элемент управления отображает меню не меню.  
  
 На следующем рисунке показано диалоговое окно содержит элемент управления страничного навигатора и элемент управления SplitButton (1). (2) стрелку раскрывающегося списка уже был выбран, и отображается подменю (3).  
  
 ![Диалоговое окно с элементом управления splitbutton и на пейджер. ] (../../mfc/reference/media/splitbutton_pager.png "splitbutton_pager")  
  
### <a name="example"></a>Пример  
 Первый оператор в следующем примере кода демонстрируется [CSplitButton::SetDropDownMenu](#setdropdownmenu) метод. Мы создали меню с Visual Studio редактор ресурсов, который автоматически с именем идентификатора панели меню, `IDR_MENU1`. `nSubMenuId` Параметр, который равен нулю, относится только вложенного меню в строке меню.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s&#2;1](../../mfc/reference/codesnippet/cpp/csplitbutton-class_1.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Класс CSplitButton](../../mfc/reference/csplitbutton-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CButton](../../mfc/reference/cbutton-class.md)

