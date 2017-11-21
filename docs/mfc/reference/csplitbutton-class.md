---
title: "Класс CSplitButton | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSplitButton
- AFXCMN/CSplitButton
- AFXCMN/CSplitButton::CSplitButton
- AFXCMN/CSplitButton::Create
- AFXCMN/CSplitButton::SetDropDownMenu
- AFXCMN/CSplitButton::OnDropDown
dev_langs: C++
helpviewer_keywords:
- CSplitButton [MFC], CSplitButton
- CSplitButton [MFC], Create
- CSplitButton [MFC], SetDropDownMenu
- CSplitButton [MFC], OnDropDown
ms.assetid: 6844d0a9-6408-4e44-9b5f-57628ed8bad6
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1235006856831c97de436a9f2b10d4aa1ad65852
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="csplitbutton-class"></a>Класс CSplitButton
`CSplitButton` Класс представляет элемент управления SplitButton. Элемент управления "кнопка разделения" реализует поведение по умолчанию, когда пользователь щелкает основную часть кнопки, и отображает раскрывающееся меню, когда пользователь щелкает раскрывающуюся стрелку кнопки.  
  
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
|[CSplitButton::Create](#create)|Создает элемент управления SplitButton с указанным стилем и прикрепляет его к текущему `CSplitButton` объекта.|  
|[CSplitButton::SetDropDownMenu](#setdropdownmenu)|Задает раскрывающееся меню, которое отображается, когда пользователь щелкает стрелку раскрывающегося списка для текущего управления SplitButton.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSplitButton::OnDropDown](#ondropdown)|Обрабатывает `BCN_DROPDOWN` уведомление, которое система отправляет, когда пользователь щелкает стрелку раскрывающегося списка для текущего управления SplitButton.|  
  
## <a name="remarks"></a>Примечания  
 `CSplitButton` Класс является производным от [CButton](../../mfc/reference/cbutton-class.md) класса. Элемент управления SplitButton используется элемент управления button, имеющих стиль `BS_SPLITBUTTON`. Пользовательское меню отображается в том случае, когда пользователь щелкает стрелку раскрывающегося списка. Дополнительные сведения см. в разделе `BS_SPLITBUTTON` и `BS_DEFSPLITBUTTON` стили [стили кнопок](http://msdn.microsoft.com/library/windows/desktop/bb775951).  
  
 На следующем рисунке показано диалоговое окно, содержит элемент управления страничного навигатора и элемент управления button (1) разбиения. Уже была нажата стрелку раскрывающегося списка (2) и (3) подменю отображается.  
  
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
  
 Дополнительные требования к этому классу, описаны в [построения требования для общих элементов управления Windows Vista](../../mfc/build-requirements-for-windows-vista-common-controls.md).  
  
##  <a name="create"></a>CSplitButton::Create  
 Создает элемент управления SplitButton с указанным стилем и прикрепляет его к текущему `CSplitButton` объекта.  
  
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
|[in] `dwStyle`|Побитовое сочетание (OR) стили, чтобы применить к элементу управления. Дополнительные сведения см. в разделе [стили кнопок](../../mfc/reference/styles-used-by-mfc.md#button-styles).|  
|[in] `rect`|Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, содержащая положение и размер элемента управления.|  
|[in] `pParentWnd`|Ненулевой указатель [CWnd](../../mfc/reference/cwnd-class.md) объекта, родительского окна элемента управления.|  
|[in] `nID`|Идентификатор элемента управления.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если этот метод выполнен успешно; в противном случае `false`.  
  
##  <a name="csplitbutton"></a>CSplitButton::CSplitButton  
 Создает объект `CSplitButton`. Параметры конструктора укажите подменю, который отображается, когда пользователь щелкает стрелку раскрывающегося списка элемента управления SplitButton.  
  
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
|[in] `nSubMenuId`|Идентификатор ресурса подменю.|  
|[in] `pMenu`|Указатель на [CMenu](../../mfc/reference/cmenu-class.md) , указывающий подменю. `CSplitButton` Объекта удалений `CMenu` и ассоциированные с ним `HMENU` при `CSplitButton` объект выходит за пределы области.|  
  
### <a name="remarks"></a>Примечания  
 Используйте [CSplitButton::Create](#create) метод, чтобы создать элемент управления SplitButton и присоединить его к `CSplitButton` объекта.  
  
##  <a name="ondropdown"></a>CSplitButton::OnDropDown  
 Обрабатывает `BCN_DROPDOWN` уведомление, которое система отправляет, когда пользователь щелкает стрелку раскрывающегося списка для текущего управления SplitButton.  
  
```  
afx_msg void OnDropDown(
    NMHDR* pNMHDR,   
    LRESULT* pResult);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `pNMHDR`|Указатель на [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) структуру, содержащую сведения о [BCN_DROPDOWN](http://msdn.microsoft.com/library/windows/desktop/bb775983) уведомления.|  
|[выходной] `pResult`|(Не используется; значение не возвращается). Возвращаемое значение [BCN_DROPDOWN](http://msdn.microsoft.com/library/windows/desktop/bb775983) уведомления.|  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь щелкает стрелку раскрывающегося списка на кнопке разбиение, система отправляет `BCN_DROPDOWN` уведомления сообщений, в котором `OnDropDown` метод обрабатывает. Тем не менее `CSplitButton` объекта не пересылает `BCN_DROPDOWN` уведомление, чтобы элемент управления, содержащий элемент управления SplitButton. Следовательно контейнерный элемент управления не поддерживает пользовательские действия в ответ на уведомление.  
  
 Для реализации настраиваемого действия, содержащего элемент управления поддерживает используйте [CButton](../../mfc/reference/cbutton-class.md) объект со стилем `BS_SPLITBUTTON` вместо `CSplitButton` объекта. Затем Реализуйте обработчик `BCN_DROPDOWN` уведомления в `CButton` объекта. Дополнительные сведения см. в разделе [стили кнопок](../../mfc/reference/styles-used-by-mfc.md#button-styles).  
  
 Чтобы реализовать пользовательское действие, что Разворачивающаяся кнопка самого элемента управления поддерживает, используйте [сообщений отражения](../../mfc/tn062-message-reflection-for-windows-controls.md). Создайте производный класс из `CSplitButton` класса и назовите его, например, CMySplitButton. Затем добавьте следующие схемы сообщений в приложение для обработки `BCN_DROPDOWN` уведомления:  
  
```  
BEGIN_MESSAGE_MAP(CMySplitButton,
    CSplitButton)  
    ON_NOTIFY_REFLECT(BCN_DROPDOWN, &CMySplitButton::OnDropDown)  
END_MESSAGE_MAP()  
```  
  
##  <a name="setdropdownmenu"></a>CSplitButton::SetDropDownMenu  
 Задает раскрывающееся меню, которое отображается, когда пользователь щелкает стрелку раскрывающегося списка для текущего управления SplitButton.  
  
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
|[in] `nSubMenuId`|Идентификатор ресурса подменю.|  
|[in] `pMenu`|Указатель на [CMenu](../../mfc/reference/cmenu-class.md) , указывающий подменю. `CSplitButton` Объекта удалений `CMenu` и ассоциированные с ним `HMENU` при `CSplitButton` объект выходит за пределы области.|  
  
### <a name="remarks"></a>Примечания  
 `nMenuId` Идентифицирует строки меню, который представляет собой горизонтальной список элементов меню. `nSubMenuId` Параметр является отсчитываемый от нуля номер индекса, который идентифицирует подменю раскрывающемся списке пунктов меню, связанные с каждой позиции строки меню. Например стандартное приложение имеет меню, содержащее элементы панели меню «Файл», «Изменить» и «Справка». Элемент панели меню «Файл» имеет, содержащий пункты меню, подменю «Открыть», «Закрыть» и «Exit». При щелчке стрелки раскрывающегося списка разворачивающуюся кнопку элемента управления в элемент управления отображает меню не меню.  
  
 На следующем рисунке показано диалоговое окно, содержит элемент управления страничного навигатора и элемент управления button (1) разбиения. Уже была нажата стрелку раскрывающегося списка (2) и (3) подменю отображается.  
  
 ![Диалоговое окно с элементом управления splitbutton и на пейджер. ] (../../mfc/reference/media/splitbutton_pager.png "splitbutton_pager")  
  
### <a name="example"></a>Пример  
 Первый оператор в следующем примере кода демонстрируется [CSplitButton::SetDropDownMenu](#setdropdownmenu) метод. Мы создали меню с Visual Studio редактор ресурсов, который автоматически присваивается имя идентификатора панели меню, `IDR_MENU1`. `nSubMenuId` Параметр, который равен нулю, ссылается на единственный вложенного меню в строке меню.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/csplitbutton-class_1.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Класс CSplitButton](../../mfc/reference/csplitbutton-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CButton](../../mfc/reference/cbutton-class.md)
