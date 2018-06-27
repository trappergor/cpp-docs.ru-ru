---
title: Класс CDockState | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CDockState [MFC], Clear
- CDockState [MFC], GetVersion
- CDockState [MFC], LoadState
- CDockState [MFC], SaveState
- CDockState [MFC], m_arrBarInfo
ms.assetid: 09e7c10b-3abd-4cb2-ad36-42420fe6bc36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 83ae0a746e31c211517563a018e5b7da18e3350a
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36955600"
---
# <a name="cdockstate-class"></a>Класс CDockState
Сериализуемый класс `CObject` для загрузки, выгрузки или очистки состояния одной или нескольких закрепляемых панелей элементов управления в постоянной памяти (файле).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDockState : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDockState::Clear](#clear)|Удаляет сведения о состоянии закрепления.|  
|[CDockState::GetVersion](#getversion)|Возвращает номер версии сохраненного состояния панели.|  
|[CDockState::LoadState](#loadstate)|Извлекает сведения о состоянии из реестра или. INI-файл.|  
|[CDockState::SaveState](#savestate)|Сохраняет сведения о состоянии для реестра и INI-файл.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDockState::m_arrBarInfo](#m_arrbarinfo)|Массив указателей на сохраненный закрепить сведения о состоянии, по одной записи для каждой панели элементов управления.|  
  
## <a name="remarks"></a>Примечания  
 Состояние закрепления включает размер и положение в строке, и того, является ли она закреплена. При получении сохраненного закрепить состояние, `CDockState` проверяет панель положение и, если строка не отображается с текущими настройками экрана `CDockState` масштабирует панели размещения таким образом, чтобы он был виден. Основная цель `CDockState` для хранения всего состояние число панелей элементов управления и чтобы разрешить это состояние сохраняется и загрузила либо в реестре, приложение в. INI-файл или в двоичной форме, как часть `CArchive` содержимое объекта.  
  
 Строке может быть любой фиксируемый элемент управления, линейчатые, включая панель инструментов, строка состояния или диалогового окна. `CDockState` объекты записи и чтения в или из него в файл с помощью `CArchive` объекта.  
  
 [CFrameWnd::GetDockState](../../mfc/reference/cframewnd-class.md#getdockstate) получает данные о состоянии всех окна фрейма в `CControlBar` объектов и помещает его в `CDockState` объекта. После этого можно написать содержимое `CDockState` объекта в хранилище с [сериализации](../../mfc/reference/cobject-class.md#serialize) или [CDockState::SaveState](#savestate). Если позднее вы хотите восстановить состояние панелей элементов управления в окне фрейма, можно загрузить в состояние с `Serialize` или [CDockState::LoadState](#loadstate), затем с помощью [CFrameWnd::SetDockState](../../mfc/reference/cframewnd-class.md#setdockstate) для применения сохраненного состояние в фрейме окна панели элементов управления.  
  
 Дополнительные сведения о закрепляемых панелей элементов управления см. в статьях [панелей элементов управления](../../mfc/control-bars.md), [панели инструментов: закрепленные и плавающие](../../mfc/docking-and-floating-toolbars.md), и [фреймов](../../mfc/frame-windows.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDockState`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxadv.h  
  
##  <a name="clear"></a>  CDockState::Clear  
 Вызывайте эту функцию, чтобы очистить все сведения о закреплении, хранящиеся в `CDockState` объекта.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Примечания  
 Это включает не только ли панель закреплена или нет, но размер и положение панели и ли он отображается.  
  
##  <a name="getversion"></a>  CDockState::GetVersion  
 Эта функция вызывается для получения номер версии сохраненного состояния панели.  
  
```  
DWORD GetVersion();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 1, если строке хранимые сведения старше текущей строки состояния; 2, если строке хранимые сведения совпадает со значением текущей строке состояния.  
  
### <a name="remarks"></a>Примечания  
 Поддержка версий позволяет исправленной строки для добавления новых свойств постоянных и по-прежнему сможет обнаружить и загрузить постоянное состояние, созданные в более ранней версии строки.  
  
##  <a name="loadstate"></a>  CDockState::LoadState  
 Эта функция вызывается для получения сведений о состоянии из реестра или. INI-файл.  
  
```  
void LoadState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszProfileName*  
 Указатель null teminated строка, указывающая имя раздела в файле инициализации или ключ в реестре Windows, где хранятся сведения о состоянии.  
  
### <a name="remarks"></a>Примечания  
 Имя профиля — часть приложения. INI-файл или реестра, содержащий сведения о состоянии на панели. Панель сведений о состоянии элементов управления можно сохранить в реестре или. INI-файл с `SaveState`.  
  
##  <a name="m_arrbarinfo"></a>  CDockState::m_arrBarInfo  
 Объект `CPtrArray` объект, который является массивом из ссылки на сведения о панели управления хранимых для каждой панели элементов управления, который сохранен сведений о состоянии в `CDockState` объекта.  
  
```  
CPtrArray m_arrBarInfo;  
```  
  
##  <a name="savestate"></a>  CDockState::SaveState  
 Эта функция вызывается для сохранения сведений о состоянии в реестре или. INI-файл.  
  
```  
void SaveState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszProfileName*  
 Указатель null teminated строка, указывающая имя раздела в файле инициализации или ключ в реестре Windows, где хранятся сведения о состоянии.  
  
### <a name="remarks"></a>Примечания  
 Имя профиля — часть приложения. INI-файл или реестра, содержащий сведения о состоянии на панели управления. `SaveState` Сохраняет текущий размер экрана. Сведения о панели управления можно получить из реестра или. INI-файл с `LoadState`.  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)

