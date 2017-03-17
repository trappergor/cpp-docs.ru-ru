---
title: "Класс CCachedDataPathProperty | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::m_Cache
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], asynchronous
- CCachedDataPathProperty class
- OLE controls [C++], asynchronous
- asynchronous controls [C++]
- memory files [C++]
ms.assetid: 0d81356b-4fe5-43f6-aed2-2eb5a5485706
caps.latest.revision: 22
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
ms.openlocfilehash: 6e3f54e6429456be24cbe18471abd1705bbe0034
ms.lasthandoff: 02/24/2017

---
# <a name="ccacheddatapathproperty-class"></a>Класс CCachedDataPathProperty
Реализует свойство элемента управления OLE, асинхронно переданного и кэшированного в файле памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CCachedDataPathProperty : public CDataPathProperty  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCachedDataPathProperty::CCachedDataPathProperty](#ccacheddatapathproperty)|Создает объект `CCachedDataPathProperty`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCachedDataPathProperty::m_Cache](#m_cache)|`CMemFile`объект для кэширования данных.|  
  
## <a name="remarks"></a>Примечания  
 В памяти файла хранятся в оперативной памяти, а не на диске и полезен для быстрого временного передачи.  
  
 Вместе с **CAysncMonikerFile** и `CDataPathProperty`, `CCachedDataPathProperty` предоставляет функциональные возможности для использования асинхронных моникеров в элементах управления OLE. С `CCachedDataPathProperty` объектов можно асинхронно передавать данные из источника URL-адрес или файл и сохраните его в файл памяти с помощью `m_Cache` общей переменной. Все данные хранятся в памяти файла, и нет необходимости переопределять [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable) Если не требуется отслеживать уведомления и отвечать. Например, при передаче больших. GIF-файл и необходимо уведомить элемент управления, что получены дополнительные данные, и он должен выполнить перерисовку, переопределить `OnDataAvailable` вносить уведомления.  
  
 Класс `CCachedDataPathProperty` является производным от `CDataPathProperty`.  
  
 Дополнительные сведения о способах использования асинхронных моникеров и элементы управления ActiveX в веб-приложений см. следующие разделы:  
  
- [Интернете первые шаги: Элементы управления ActiveX](../../mfc/activex-controls-on-the-internet.md)  
  
- [Internet первые шаги: Асинхронные моникеры](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)  
  
 `CCachedDataPathProperty`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxctl.h  
  
##  <a name="ccacheddatapathproperty"></a>CCachedDataPathProperty::CCachedDataPathProperty  
 Создает объект `CCachedDataPathProperty`.  
  
```  
CCachedDataPathProperty(COleControl* pControl = NULL);

 
CCachedDataPathProperty(
    LPCTSTR lpszPath,  
    COleControl* pControl = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pControl`  
 Указатель на объект элемента управления ActiveX, связываемого с данным `CCachedDataPathProperty` объекта.  
  
 `lpszPath`  
 Путь, который может быть абсолютным или относительным, используется для создания асинхронных моникер, ссылающийся на фактическое расположение абсолютный свойства. `CCachedDataPathProperty`использует URL-адреса, не имена файлов. Если вы хотите `CCachedDataPathProperty` объекта для файла, начало file:// пути.  
  
### <a name="remarks"></a>Примечания  
 `COleControl` Объекта, на который указывает `pControl` используется [откройте](../../mfc/reference/cdatapathproperty-class.md#open) и получить производными классами. Если `pControl` — **NULL**, элемент управления, используемый с **откройте** должно быть задано значение [SetControl](../../mfc/reference/cdatapathproperty-class.md#setcontrol). Если `lpszPath` — **NULL**, можно передать путь через **откройте** или настроить ее с помощью [SetPath](../../mfc/reference/cdatapathproperty-class.md#setpath).  
  
##  <a name="m_cache"></a>CCachedDataPathProperty::m_Cache  
 Содержит имя класса в файл памяти, в который кэшируются данные.  
  
```  
CMemFile m_Cache;  
```  
  
### <a name="remarks"></a>Примечания  
 Файл памяти хранятся в оперативной памяти, а не на диске.  
  
## <a name="see-also"></a>См. также  
 [Класс CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)

