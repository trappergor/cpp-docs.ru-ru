---
title: "Класс CMFCCmdUsageCount | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCCmdUsageCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::AddCmd
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::GetCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::HasEnoughInformation
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::IsFreqeuntlyUsedCmd
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::Reset
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::Serialize
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::SetOptions
dev_langs:
- C++
helpviewer_keywords:
- CMFCCmdUsageCount class
ms.assetid: 9c33b783-37c0-43ea-9f31-3c75e246c841
caps.latest.revision: 20
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
ms.openlocfilehash: b264448af4041139018b181e2255988555267b89
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccmdusagecount-class"></a>Класс CMFCCmdUsageCount
Отслеживает счетчик использования сообщений Windows, например, при выборе пользователем элемента меню.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCCmdUsageCount : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|`CMFCCmdUsageCount::CMFCCmdUsageCount`|Конструктор по умолчанию.|  
|`CMFCCmdUsageCount::~CMFCCmdUsageCount`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCCmdUsageCount::AddCmd](#addcmd)|Увеличивает на единицу счетчик, который связан с данной команды.|  
|[CMFCCmdUsageCount::GetCount](#getcount)|Получает счетчик использования, связанный с данной команды.|  
|[CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation)|Определяет, собираются ли этот объект минимальный объем данных отслеживания.|  
|[CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd)|Определяет, используется ли данной команды часто.|  
|[CMFCCmdUsageCount::Reset](#reset)|Удаляет счетчик использования всех команд.|  
|[CMFCCmdUsageCount::Serialize](#serialize)|Считывает этот объект из архива и записывает его в архив. (Переопределяет [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CMFCCmdUsageCount::SetOptions](#setoptions)|Общие наборы значений `CMFCCmdUsageCount` данные-члены класса.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|Имя|Описание|  
|`m_CmdUsage`|Объект `CMap` объект, который сопоставляет команды счетчики их использования.|  
|`m_nMinUsagePercentage`|Процент минимальное использование часто используемые команды.|  
|`m_nStartCount`|Запуск счетчик, который используется для определения, ли этот объект сбор минимальный объем данных отслеживания.|  
|`m_nTotalUsage`|Количество всех отслеживаемых команд.|  
  
### <a name="remarks"></a>Примечания  
 `CMFCCmdUsageCount` Сопоставляет класс каждый числовой идентификатор сообщения Windows счетчика 32-разрядное целое число без знака. `CMFCToolBar`Этот класс используется для отображения часто используемые элементы. Дополнительные сведения о `CMFCToolBar`, в разделе [CMFCToolBar класса](../../mfc/reference/cmfctoolbar-class.md).  
  
 Можно сохранить `CMFCCmdUsageCount` класса данных между выполнениями программы. Используйте [CMFCCmdUsageCount::Serialize](#serialize) метод сериализации данных члена класса и [CMFCCmdUsageCount::SetOptions](#setoptions) метод, чтобы задать общий член данных.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCCmdUsageCount](../../mfc/reference/cmfccmdusagecount-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmdusagecount.h  
  
##  <a name="addcmd"></a>CMFCCmdUsageCount::AddCmd  
 Увеличивает на единицу счетчик, который связан с данной команды.  
  
```  
void AddCmd(UINT uiCmd);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `uiCmd`|Указывает команду счетчик будет изменяться.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод добавляет новую запись к структуре карты количество команд `m_CmdUsage`, если запись еще не существует.  
  
 Этот метод не выполняет никаких действий в следующих случаях:  
  
-   Панель инструментов framework находится в режиме настройки ( [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode) метод возвращает ненулевое значение).  
  
-   Команда ссылается на вложенного меню или меню разделителя ( `uiCmd` равно 0 или -1).  
  
- `uiCmd`ссылается на стандартную команду (глобальный `IsStandardCommand` функция возвращает ненулевое значение).  
  
##  <a name="getcount"></a>CMFCCmdUsageCount::GetCount  
 Получает счетчик использования, связанный с данной команды.  
  
```  
UINT GetCount(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `uiCmd`|Идентификатор счетчика команд для извлечения.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Счетчик использования, связанный с данной команды.  
  
##  <a name="hasenoughinformation"></a>CMFCCmdUsageCount::HasEnoughInformation  
 Определяет, получил ли данный объект минимальный объем данных отслеживания.  
  
```  
BOOL HasEnoughInformation() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если этот объект получил минимально отслеживания данных; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает ненулевое значение, если общее число `m_nTotalUsage`, все отслеживаемые команд или равно больше, чем исходное значение счетчика `m_nStartCount`. По умолчанию платформа задает начальное число 0. Это значение можно переопределить с помощью [CMFCCmdUsageCount::SetOptions](#setoptions) метод.  
  
 Этот метод используется [CMFCMenuBar::IsShowAllCommands](../../mfc/reference/cmfcmenubar-class.md#isshowallcommands) для определения необходимости отображение всех команд меню.  
  
##  <a name="isfreqeuntlyusedcmd"></a>CMFCCmdUsageCount::IsFreqeuntlyUsedCmd  
 Определяет, используется ли данной команды часто.  
  
```  
BOOL IsFreqeuntlyUsedCmd(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `uiCmd`|Указывает команду для проверки.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если команда часто используется; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает 0, если использование всего команды, `m_nTotalUsage`, равно 0. В противном случае, этот метод возвращает ненулевое значение, если процент, который используется указанная команда больше, чем минимальный процент `m_nMinUsagePercentage`. По умолчанию платформа задает минимальный процент до 5. Это значение можно переопределить с помощью [CMFCCmdUsageCount::SetOptions](#setoptions) метод. Если минимальное значение равно 0, этот метод возвращает ненулевое значение, если указанная команда число больше 0.  
  
 [CMFCToolBar::IsCommandRarelyUsed](../../mfc/reference/cmfctoolbar-class.md#iscommandrarelyused) этот метод используется для определения ли команда используется редко.  
  
##  <a name="reset"></a>CMFCCmdUsageCount::Reset  
 Удаляет счетчик использования всех команд.  
  
```  
void Reset();
```  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы очистить все записи из структуры карты счетчиков команда `m_CmdUsage`и сбросить использование всего команды, `m_nTotalUsage`, счетчика на 0.  
  
##  <a name="serialize"></a>CMFCCmdUsageCount::Serialize  
 Считывает этот объект из архива и записывает его в архив.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `ar`|Объект `CArchive` объект для сериализации или к нему.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод сериализует структуры карты счетчиков команда `m_CmdUsage`и использование всего команды, `m_nTotalUsage`, счетчик или для архива.  
  
 Примеры сериализации см. в разделе [сериализация: сериализация объекта](../../mfc/serialization-serializing-an-object.md).  
  
##  <a name="setoptions"></a>CMFCCmdUsageCount::SetOptions  
 Общие наборы значений `CMFCCmdUsageCount` данные-члены класса.  
  
```  
static BOOL __stdcall SetOptions(
    UINT nStartCount,  
    UINT nMinUsagePercentage);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `nStartCount`|Новый счетчик начальной все записанные команды.|  
|[in] `nMinUsagePercentage`|Новое значение процента минимальное использование.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод выполнен успешно, `FALSE` Если `nMinUsagePercentage` параметр больше или равно 100.  
  
### <a name="remarks"></a>Примечания  
 Этот метод задает общий `CMFCCmdUsageCount` данные-члены класса `m_nStartCount` и `m_nMinUsagePercentage` для `nStartCount` и `nMinUsagePercentage`соответственно. `m_nStartCount`используется [CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation) метод для определения, ли этот объект сбор минимальный объем данных отслеживания. `m_nMinUsagePercentage`используется [CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd) метод для определения данной команды часто.  
  
 В отладочном построении этот метод создает ошибку подтверждения, если `nMinUsagePercentage` параметр больше или равно 100.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

