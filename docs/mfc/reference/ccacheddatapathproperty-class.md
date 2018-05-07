---
title: Класс CCachedDataPathProperty | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::m_Cache
dev_langs:
- C++
helpviewer_keywords:
- CCachedDataPathProperty [MFC], CCachedDataPathProperty
- CCachedDataPathProperty [MFC], m_Cache
ms.assetid: 0d81356b-4fe5-43f6-aed2-2eb5a5485706
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 29e46f7e65d6c2f9b5c0d29007cd31f660754957
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ccacheddatapathproperty-class"></a>Класс CCachedDataPathProperty
Реализует свойство элемента управления OLE, асинхронно переданного и кэшированного в файле памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CCachedDataPathProperty : public CDataPathProperty  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCachedDataPathProperty::CCachedDataPathProperty](#ccacheddatapathproperty)|Создает объект `CCachedDataPathProperty`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCachedDataPathProperty::m_Cache](#m_cache)|`CMemFile` объект для кэширования данных.|  
  
## <a name="remarks"></a>Примечания  
 Файл памяти хранятся в оперативной памяти, а не на диске и полезен для быстрого временного передачи.  
  
 Вместе с **CAysncMonikerFile** и `CDataPathProperty`, `CCachedDataPathProperty` предоставляет функциональные возможности для использования асинхронных моникеров в элементах управления OLE. С `CCachedDataPathProperty` объектов можно асинхронно передавать данные из источника URL-адрес или файл и сохраните его в памяти файл с помощью `m_Cache` общей переменной. Все данные хранятся в файле памяти, и нет необходимости переопределять [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable) Если не требуется отслеживать уведомления и ответ. Например, при передаче большого. GIF-файл и необходимо уведомить элемент управления перерисовывать себя, что получены дополнительные данные переопределения `OnDataAvailable` вносить уведомления.  
  
 Класс `CCachedDataPathProperty` является производным от `CDataPathProperty`.  
  
 Дополнительные сведения о способах использования асинхронных моникеров и элементы управления ActiveX в веб-приложений см. в следующих разделах:  
  
- [Интернете первые шаги: Элементы управления ActiveX](../../mfc/activex-controls-on-the-internet.md)  
  
- [Интернете первые шаги: Асинхронные моникеры](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
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
  
##  <a name="ccacheddatapathproperty"></a>  CCachedDataPathProperty::CCachedDataPathProperty  
 Создает объект `CCachedDataPathProperty`.  
  
```  
CCachedDataPathProperty(COleControl* pControl = NULL);

 
CCachedDataPathProperty(
    LPCTSTR lpszPath,  
    COleControl* pControl = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pControl`  
 Указатель на объект элемента управления ActiveX, связываемое с этим `CCachedDataPathProperty` объекта.  
  
 `lpszPath`  
 Путь, который может быть абсолютным или относительным, используется для создания асинхронных моникер, ссылающийся на фактическое расположение абсолютный свойства. `CCachedDataPathProperty` использует URL-адреса, не имена файлов. Если вы хотите `CCachedDataPathProperty` объекта для файла, добавить file:// в путь.  
  
### <a name="remarks"></a>Примечания  
 `COleControl` Объекта, на который указывает `pControl` используется [откройте](../../mfc/reference/cdatapathproperty-class.md#open) и получить производные классы. Если `pControl` — **NULL**, элемент управления, используемый с **откройте** следует задавать с [SetControl](../../mfc/reference/cdatapathproperty-class.md#setcontrol). Если `lpszPath` — **NULL**, можно передать путь через **откройте** или установите его с [SetPath](../../mfc/reference/cdatapathproperty-class.md#setpath).  
  
##  <a name="m_cache"></a>  CCachedDataPathProperty::m_Cache  
 Содержит имя класса в памяти файла, в который кэшируются данные.  
  
```  
CMemFile m_Cache;  
```  
  
### <a name="remarks"></a>Примечания  
 Файл памяти хранятся в оперативной памяти, а не на диске.  
  
## <a name="see-also"></a>См. также  
 [Класс CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)
