---
title: "Класс CMFCRibbonQuickAccessToolBarDefaultState | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::AddCommand
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState class
ms.assetid: eca99200-b87b-47ba-b2e8-2f3f2444b176
caps.latest.revision: 28
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 211e8d897de923e7f07df389b0e9e7218cf45872
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonquickaccesstoolbardefaultstate-class"></a>Класс CMFCRibbonQuickAccessToolBarDefaultState
Вспомогательный класс, который управляет состоянием по умолчанию для быстрого доступа, которая расположена на ленте ( [класса CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonQuickAccessToolBarDefaultState  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState](#cmfcribbonquickaccesstoolbardefaultstate)|Создает объект `CMFCRibbonQuickAccessToolbarDefaultState`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand)|Добавляет команду в состояние по умолчанию для быстрого доступа. Панели инструментов, сам не меняется.|  
|[CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom](#copyfrom)|Копирует свойства из одной панели быстрого доступа к другому.|  
|[CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll](#removeall)|Удаляет все команды из панели быстрого доступа. Панели инструментов, сам не меняется.|  
  
## <a name="remarks"></a>Примечания  
 После создания панели инструментов быстрого доступа в приложении, рекомендуется установить состояние по умолчанию путем вызова [CMFCRibbonBar::SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate). Это состояние по умолчанию восстанавливается в том случае, когда пользователь щелкает **Сброс** кнопку **Настройка** страницу приложения **параметры** диалоговое окно.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CMFCRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md)  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует создания объекта `CMFCRibbonQuickAccessToolbarDefaultState` класс и как добавить команды в состояние по умолчанию для быстрого доступа.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#21;](../../mfc/reference/codesnippet/cpp/cmfcribbonquickaccesstoolbardefaultstate-class_1.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxribbonquickaccesstoolbar.h  
  
##  <a name="addcommand"></a>CMFCRibbonQuickAccessToolBarDefaultState::AddCommand  
 Добавляет команду в состояние по умолчанию для быстрого доступа.  
  
```  
void AddCommand(
    UINT uiCmd,  
    BOOL bIsVisible=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `[in] uiCmd`  
 Указывает идентификатор команды.  
  
 `[in] bIsVisible`  
 Задает видимость для команды, когда панель быстрого доступа находится в состоянии по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Добавление команды на CMFCRibbonQuickAccessToolBarDefaultState выполняет три результата. Во-первых каждой добавлены команды отображается раскрывающийся список справа от панели инструментов быстрого доступа. Таким образом пользователь может простое добавление и удаление команды из панели быстрого доступа. Во-вторых, панель быстрого доступа сбрасывается для отображения только тех команд, которые перечислены как видимый в состоянии по умолчанию при нажатии **Сброс** кнопки в **Настройка** диалоговое окно. Третий, если не был вызван [CMFCRibbonBar::SetQuickAccessCommands](../../mfc/reference/cmfcribbonbar-class.md#setquickaccesscommands), панель быстрого доступа использует видимыми команды из этого списка как команд, отображаемых по умолчанию при первом запуске приложения пользователем. После добавления всех команд, которые требуется вызвать [CMFCRibbonBar::SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate) устанавливаемого этот экземпляр в качестве состояния по умолчанию для быстрого доступа, ленты.  
  
##  <a name="copyfrom"></a>CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom  
 Копирует свойства из одной панели быстрого доступа к другому.  
  
```  
void CopyFrom(const CMFCRibbonQuickAccessToolBarDefaultState& src);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `src`  
 Ссылка на источник `CMFCRibbonQuickAccessToolBarDefaultState` для копирования.  
  
### <a name="remarks"></a>Примечания  
 Этот метод копирует каждую команду из источника `CMFCRibbonQuickAccessToolBarDefaultState` объект, подлежащий сравнению с помощью [CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand) метод.  
  
##  <a name="cmfcribbonquickaccesstoolbardefaultstate"></a>CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState  
 Создает объект состояния по умолчанию панель быстрого доступа.  
  
```  
CMFCRibbonQuickAccessToolBarDefaultState();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию список команд, новый экземпляр [CMFRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md) содержит пуст.  
  
##  <a name="removeall"></a>CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll  
 Очищает список команд по умолчанию в панели инструментов быстрого доступа.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция удаляет из этого экземпляра все команды, предыдущими вызовами [CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand) добавлена.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)

