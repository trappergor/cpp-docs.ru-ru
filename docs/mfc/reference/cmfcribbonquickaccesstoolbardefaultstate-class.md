---
title: Класс CMFCRibbonQuickAccessToolBarDefaultState | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], CMFCRibbonQuickAccessToolBarDefaultState
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], AddCommand
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], CopyFrom
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], RemoveAll
ms.assetid: eca99200-b87b-47ba-b2e8-2f3f2444b176
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a9fd8c983e0133644b6531e87f5fc1dec0fdc7b7
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2018
ms.locfileid: "37041809"
---
# <a name="cmfcribbonquickaccesstoolbardefaultstate-class"></a>Класс CMFCRibbonQuickAccessToolBarDefaultState
Вспомогательный класс, который управляет состоянием по умолчанию для быстрого доступа, расположенный на панели ленты ( [CMFCRibbonBar класса](../../mfc/reference/cmfcribbonbar-class.md)).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonQuickAccessToolBarDefaultState  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState](#cmfcribbonquickaccesstoolbardefaultstate)|Создает объект `CMFCRibbonQuickAccessToolbarDefaultState`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand)|Добавляет команду в состояние по умолчанию для быстрого доступа. Сама панель остается неизменным.|  
|[CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom](#copyfrom)|Копирует свойства одного быстрого доступа к другому.|  
|[CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll](#removeall)|Удаляет все команды из панели инструментов быстрого доступа. Сама панель остается неизменным.|  
  
## <a name="remarks"></a>Примечания  
 После создания панели инструментов быстрого доступа в приложении, рекомендуется установить состояние по умолчанию путем вызова [CMFCRibbonBar::SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate). Это состояние по умолчанию восстанавливается в том случае, когда пользователь щелкает **Сброс** кнопку **Настройка** страница приложения **параметры** диалоговое окно.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CMFCRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md)  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует создание объекта `CMFCRibbonQuickAccessToolbarDefaultState` класс и как добавить команды в состояние по умолчанию для быстрого доступа.  
  
 [!code-cpp[NVC_MFC_RibbonApp#21](../../mfc/reference/codesnippet/cpp/cmfcribbonquickaccesstoolbardefaultstate-class_1.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxribbonquickaccesstoolbar.h  
  
##  <a name="addcommand"></a>  CMFCRibbonQuickAccessToolBarDefaultState::AddCommand  
 Добавляет команду в состояние по умолчанию для быстрого доступа.  
  
```  
void AddCommand(
    UINT uiCmd,  
    BOOL bIsVisible=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *[in] uiCmd*  
 Указывает идентификатор команды.  
  
 *[in] bIsVisible*  
 Задает видимость команды, когда панель быстрого доступа находится в состоянии по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Добавление команды CMFCRibbonQuickAccessToolBarDefaultState выполняет три результаты. Во-первых каждая команда добавлены значится на раскрывающийся список справа от панели инструментов быстрого доступа. Таким образом пользователь легко можно добавить или удалить команды из панели инструментов быстрого доступа. Во-вторых, панели инструментов быстрого доступа будет сброшен для отображения только тех команд, которые перечислены как видимый в состоянии по умолчанию при щелчке **Сброс** кнопку в **Настройка** диалоговое окно. Третий, если не был вызван [CMFCRibbonBar::SetQuickAccessCommands](../../mfc/reference/cmfcribbonbar-class.md#setquickaccesscommands), панели инструментов быстрого доступа использует видимые команды из этого списка, как видимые команды по умолчанию при первом запуске приложения пользователем. После добавления всех команд, которые нужно вызвать [CMFCRibbonBar::SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate) для установки данного экземпляра в качестве режима по умолчанию для быстрого доступа, панели ленты.  
  
##  <a name="copyfrom"></a>  CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom  
 Копирует свойства одного быстрого доступа к другому.  
  
```  
void CopyFrom(const CMFCRibbonQuickAccessToolBarDefaultState& src);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *src*  
 Ссылка на источник `CMFCRibbonQuickAccessToolBarDefaultState` объект для копирования из.  
  
### <a name="remarks"></a>Примечания  
 Этот метод копирует каждой команды из источника `CMFCRibbonQuickAccessToolBarDefaultState` объекта к данному объекту с помощью [CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand) метод.  
  
##  <a name="cmfcribbonquickaccesstoolbardefaultstate"></a>  CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState  
 Создает объект состояния по умолчанию панель быстрого доступа.  
  
```  
CMFCRibbonQuickAccessToolBarDefaultState();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию список команд, новый экземпляр [CMFRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md) содержит пуст.  
  
##  <a name="removeall"></a>  CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll  
 Очищает список команд по умолчанию в панели инструментов быстрого доступа.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция удаляет из данного экземпляра, все команды, предыдущие вызовы [CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand) добавлен.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)
