---
title: "Класс CMFCCmdUsageCount | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
- CMFCCmdUsageCount [MFC], AddCmd
- CMFCCmdUsageCount [MFC], GetCount
- CMFCCmdUsageCount [MFC], HasEnoughInformation
- CMFCCmdUsageCount [MFC], IsFreqeuntlyUsedCmd
- CMFCCmdUsageCount [MFC], Reset
- CMFCCmdUsageCount [MFC], Serialize
- CMFCCmdUsageCount [MFC], SetOptions
ms.assetid: 9c33b783-37c0-43ea-9f31-3c75e246c841
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0db24894777170d2860ba8d1639fd44e3893732a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmfccmdusagecount-class"></a>Класс CMFCCmdUsageCount
Отслеживает загруженность сообщений Windows, например когда пользователь выбирает элемент меню.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCCmdUsageCount : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание:|  
|`CMFCCmdUsageCount::CMFCCmdUsageCount`|Конструктор по умолчанию.|  
|`CMFCCmdUsageCount::~CMFCCmdUsageCount`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|Имя|Описание:|  
|[CMFCCmdUsageCount::AddCmd](#addcmd)|Увеличивает на единицу счетчик, который связан с данной команды.|  
|[CMFCCmdUsageCount::GetCount](#getcount)|Получает счетчик использования, связанный с данной команды.|  
|[CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation)|Определяет, является ли этот объект собрал минимальный объем данных отслеживания.|  
|[CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd)|Определяет, используется ли заданную команду часто.|  
|[CMFCCmdUsageCount::Reset](#reset)|Удаляет счетчик использования всех команд.|  
|[CMFCCmdUsageCount::Serialize](#serialize)|Считывает этот объект из архива или записывает его в архив. (Переопределяет [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CMFCCmdUsageCount::SetOptions](#setoptions)|Общие наборы значений `CMFCCmdUsageCount` данные-члены класса.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|name|Описание:|  
|`m_CmdUsage`|Объект `CMap` объект, который сопоставляет команды счетчики их использования.|  
|`m_nMinUsagePercentage`|Процент минимальное использование часто используемые команды.|  
|`m_nStartCount`|Начало счетчик, который используется для определения, является ли этот объект собрал минимальный объем данных отслеживания.|  
|`m_nTotalUsage`|Количество команд все отслеживаемые.|  
  
### <a name="remarks"></a>Примечания  
 `CMFCCmdUsageCount` Класс сопоставляет каждый числовой идентификатор сообщения Windows счетчика 32-разрядное целое число без знака. `CMFCToolBar`Этот класс используется для отображения элементов часто используются панели инструментов. Дополнительные сведения о `CMFCToolBar`, в разделе [CMFCToolBar класса](../../mfc/reference/cmfctoolbar-class.md).  
  
 Можно сохранить `CMFCCmdUsageCount` класса данных между выполнениями программы. Используйте [CMFCCmdUsageCount::Serialize](#serialize) метод сериализации данных члена класса и [CMFCCmdUsageCount::SetOptions](#setoptions) метод, чтобы задать общего члена данных.  
  
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
|Параметр|Описание:|  
|[in] `uiCmd`|Указывает команду счетчик будет изменяться.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод добавляет новую запись к структуре карты счетчики команда `m_CmdUsage`, если запись еще не существует.  
  
 Этот метод не выполняет никаких действий в следующих случаях:  
  
-   Панель инструментов framework устанавливается в режим настройки ( [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode) метод возвращает ненулевое значение).  
  
-   Команда ссылается на разделитель меню или подменю ( `uiCmd` равно 0 или -1).  
  
- `uiCmd`ссылается на стандартные команды (глобальный `IsStandardCommand` функция возвращает ненулевое значение).  
  
##  <a name="getcount"></a>CMFCCmdUsageCount::GetCount  
 Получает счетчик использования, связанный с данной команды.  
  
```  
UINT GetCount(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание:|  
|[in] `uiCmd`|Идентификатор счетчика команду для извлечения.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Счетчик использования, связанный с данной команды.  
  
##  <a name="hasenoughinformation"></a>CMFCCmdUsageCount::HasEnoughInformation  
 Определяет, является ли этот объект получил минимальный объем данных отслеживания.  
  
```  
BOOL HasEnoughInformation() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если этот объект получил минимальный объем данных; отслеживания в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает ненулевое значение, если общее число `m_nTotalUsage`, все отслеживаемые команд становится равным или больше, чем исходное количество `m_nStartCount`. По умолчанию платформа задает исходное значение счетчика 0. Это значение можно переопределить с помощью [CMFCCmdUsageCount::SetOptions](#setoptions) метод.  
  
 Этот метод используется [CMFCMenuBar::IsShowAllCommands](../../mfc/reference/cmfcmenubar-class.md#isshowallcommands) для определения необходимости отображение всех доступных меню команд.  
  
##  <a name="isfreqeuntlyusedcmd"></a>CMFCCmdUsageCount::IsFreqeuntlyUsedCmd  
 Определяет, используется ли заданную команду часто.  
  
```  
BOOL IsFreqeuntlyUsedCmd(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание:|  
|[in] `uiCmd`|Указывает команду для проверки.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если команда часто используется; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает 0, если используется команда итог `m_nTotalUsage`, равно 0. В противном случае этот метод возвращает ненулевое значение, если процент, из которых используется указанная команда больше, чем минимальный процент `m_nMinUsagePercentage`. По умолчанию платформа задает минимальный процент до 5. Это значение можно переопределить с помощью [CMFCCmdUsageCount::SetOptions](#setoptions) метод. Если минимальный процент равен 0, этот метод возвращает ненулевое значение, если указанная команда число больше 0.  
  
 [CMFCToolBar::IsCommandRarelyUsed](../../mfc/reference/cmfctoolbar-class.md#iscommandrarelyused) этот метод используется для определения ли команды используется редко.  
  
##  <a name="reset"></a>CMFCCmdUsageCount::Reset  
 Удаляет счетчик использования всех команд.  
  
```  
void Reset();
```  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы очистить все записи из структуры карты счетчиков команда `m_CmdUsage`и сброса использование общее команды, `m_nTotalUsage`, счетчик 0.  
  
##  <a name="serialize"></a>CMFCCmdUsageCount::Serialize  
 Считывает этот объект из архива или записывает его в архив.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание:|  
|[in] `ar`|Объект `CArchive` объект для сериализации из или в нее.|  
  
### <a name="remarks"></a>Примечания  
 Этот метод сериализует структуре карты счетчиков команда `m_CmdUsage`и об использовании общее команды, `m_nTotalUsage`, счетчик из или в указанный архив.  
  
 Примеры сериализации см. в разделе [сериализации: сериализация объекта](../../mfc/serialization-serializing-an-object.md).  
  
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
|Параметр|Описание:|  
|[in] `nStartCount`|Новое начальное количество все отслеживаемые команд.|  
|[in] `nMinUsagePercentage`|Процент новых минимальное использование.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод выполнен успешно, `FALSE` Если `nMinUsagePercentage` параметр, размер которого больше или равно 100.  
  
### <a name="remarks"></a>Примечания  
 Этот метод задает общий `CMFCCmdUsageCount` данные-члены класса `m_nStartCount` и `m_nMinUsagePercentage` для `nStartCount` и `nMinUsagePercentage`соответственно. `m_nStartCount`используется [CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation) метод, чтобы определить, является ли этот объект собрал минимальный объем данных отслеживания. `m_nMinUsagePercentage`используется [CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd) метод для определения часто использование данной команды.  
  
 В отладочных построениях этот метод создает Сбой утверждения, если `nMinUsagePercentage` параметр, размер которого больше или равно 100.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)
