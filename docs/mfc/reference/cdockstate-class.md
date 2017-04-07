---
title: "Класс CDockState | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDockState
- AFXADV/CDockState
- AFXADV/CDockState::Clear
- AFXADV/CDockState::GetVersion
- AFXADV/CDockState::LoadState
- AFXADV/CDockState::SaveState
- AFXADV/CDockState::m_arrBarInfo
dev_langs:
- C++
helpviewer_keywords:
- dock state
- size
- docking control bars
- CDockState class
- states, dockable control bar
- position, control bar
- size, control bar
- docking tool windows
ms.assetid: 09e7c10b-3abd-4cb2-ad36-42420fe6bc36
caps.latest.revision: 23
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
ms.openlocfilehash: fc8beb80cc35c1816fbc305ece2bfbc5df2e7cd0
ms.lasthandoff: 02/24/2017

---
# <a name="cdockstate-class"></a>Класс CDockState
Сериализуемый класс `CObject` для загрузки, выгрузки или очистки состояния одной или нескольких закрепляемых панелей элементов управления в постоянной памяти (файле).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDockState : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDockState::Clear](#clear)|Удаляет сведения о состоянии закрепления.|  
|[CDockState::GetVersion](#getversion)|Извлекает номер версии сохраненного состояния панели.|  
|[CDockState::LoadState](#loadstate)|Получает сведения о состоянии из реестра или. INI-файл.|  
|[CDockState::SaveState](#savestate)|Сохраняет сведения о состоянии в реестре или INI-файл.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDockState::m_arrBarInfo](#m_arrbarinfo)|Массив указателей на сохраненный закрепить сведения о состоянии по одной записи для каждой панели элементов управления.|  
  
## <a name="remarks"></a>Примечания  
 Состояние закрепления включает размер и положение в строке, и того, является ли она закреплена. При получении хранимую закрепить состояние, `CDockState` проверяет панель позиции и, если панель не отображается с текущими настройками экрана `CDockState` масштабирует панели размещения таким образом, он отображается. Основная цель `CDockState` проводить полное состояние из нескольких панелей элементов управления и разрешить это состояние для сохранения и загрузки, либо в реестре, приложения. INI-файл, или в двоичной форме как часть `CArchive` содержимое объекта.  
  
 Панель может быть любой фиксируемый элемент управления панели, включая панель инструментов, строка состояния или диалогового окна. `CDockState`объекты записи и чтения или в файл с помощью `CArchive` объекта.  
  
 [CFrameWnd::GetDockState](../../mfc/reference/cframewnd-class.md#getdockstate) получает сведения о состоянии всех окна фрейма `CControlBar` объектов и помещает его в `CDockState` объекта. После этого можно написать содержимое `CDockState` объектов в хранилище с [сериализации](../../mfc/reference/cobject-class.md#serialize) или [CDockState::SaveState](#savestate). Если позже вы хотите восстановить состояние панелей элементов управления в фрейме окна, можно загрузить состояние с `Serialize` или [CDockState::LoadState](#loadstate), затем с помощью [CFrameWnd::SetDockState](../../mfc/reference/cframewnd-class.md#setdockstate) для применения к панели элементов управления окна фрейма сохраненное состояние.  
  
 Дополнительные сведения о закрепления панели элементов управления, см. в статьях [панелей элементов управления](../../mfc/control-bars.md), [панели инструментов: закрепленные и плавающие](../../mfc/docking-and-floating-toolbars.md), и [окна фрейма](../../mfc/frame-windows.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDockState`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxadv.h  
  
##  <a name="clear"></a>CDockState::Clear  
 Вызывайте эту функцию, чтобы очистить все сведения о закреплении, хранящиеся в `CDockState` объекта.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Примечания  
 Сюда входят не только ли панель закреплена или нет, но размер и положение панели и ли он отображается.  
  
##  <a name="getversion"></a>CDockState::GetVersion  
 Эта функция вызывается для получения номер версии сохраненного состояния панели.  
  
```  
DWORD GetVersion();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 1, если панели хранимые сведения старше текущей строке состояния. 2, если панели хранимой информации совпадает с текущей строке состояния.  
  
### <a name="remarks"></a>Примечания  
 Поддержка версий позволяет исправленной строки для добавления новых свойств постоянные и по-прежнему может обнаруживать и загружать постоянное состояние, созданные в более ранней версии строки.  
  
##  <a name="loadstate"></a>CDockState::LoadState  
 Эта функция вызывается для получения сведений о состоянии из реестра или. INI-файл.  
  
```  
void LoadState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszProfileName`  
 Указатель null teminated строка, указывающая имя раздела в файле настройки или ключ в реестре Windows, где хранится информация о состоянии.  
  
### <a name="remarks"></a>Примечания  
 Имя профиля — часть приложения. INI-файл или реестр, который содержит сведения о состоянии панели элементов. Панель сведений о состоянии элементов управления можно сохранить в реестре или. INI-файл с `SaveState`.  
  
##  <a name="m_arrbarinfo"></a>CDockState::m_arrBarInfo  
 Объект `CPtrArray` объект, который представляет собой массив ссылки на сведения о панели управления хранимых для каждой панели элементов управления, который сохраненные сведения о состоянии в `CDockState` объекта.  
  
```  
CPtrArray m_arrBarInfo;  
```  
  
##  <a name="savestate"></a>CDockState::SaveState  
 Эта функция вызывается для сохранения сведений о состоянии в реестре или. INI-файл.  
  
```  
void SaveState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszProfileName`  
 Указатель null teminated строка, указывающая имя раздела в файле настройки или ключ в реестре Windows, где хранится информация о состоянии.  
  
### <a name="remarks"></a>Примечания  
 Имя профиля — часть приложения. INI-файла или реестра, содержащий сведения о состоянии на панели управления. `SaveState`Сохраняет текущий размер экрана. Сведения о панели управления можно получить из реестра или. INI-файл с `LoadState`.  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)


