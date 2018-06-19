---
title: Класс CDataPathProperty | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDataPathProperty
- AFXCTL/CDataPathProperty
- AFXCTL/CDataPathProperty::CDataPathProperty
- AFXCTL/CDataPathProperty::GetControl
- AFXCTL/CDataPathProperty::GetPath
- AFXCTL/CDataPathProperty::Open
- AFXCTL/CDataPathProperty::ResetData
- AFXCTL/CDataPathProperty::SetControl
- AFXCTL/CDataPathProperty::SetPath
dev_langs:
- C++
helpviewer_keywords:
- CDataPathProperty [MFC], CDataPathProperty
- CDataPathProperty [MFC], GetControl
- CDataPathProperty [MFC], GetPath
- CDataPathProperty [MFC], Open
- CDataPathProperty [MFC], ResetData
- CDataPathProperty [MFC], SetControl
- CDataPathProperty [MFC], SetPath
ms.assetid: 1f96efdb-54e4-460b-862c-eba5d4103488
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f2559b4917f16bb8ddc49b73ace8bda6e1a9bafc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367312"
---
# <a name="cdatapathproperty-class"></a>Класс CDataPathProperty
Реализует свойство элемента управления OLE, которое можно загрузить асинхронно.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDataPathProperty : public CAsyncMonikerFile  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDataPathProperty::CDataPathProperty](#cdatapathproperty)|Создает объект `CDataPathProperty`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDataPathProperty::GetControl](#getcontrol)|Извлекает асинхронной управления OLE, связанного с `CDataPathProperty` объекта.|  
|[CDataPathProperty::GetPath](#getpath)|Получает путь свойства.|  
|[CDataPathProperty::Open](#open)|Инициирует загрузку асинхронного свойства связанного элемента управления ActiveX (OLE).|  
|[CDataPathProperty::ResetData](#resetdata)|Вызовы `CAsyncMonikerFile::OnDataAvailable` известить контейнера, в котором изменились свойства элемента управления.|  
|[CDataPathProperty::SetControl](#setcontrol)|Задает асинхронной элемента управления ActiveX (OLE), связанного со свойством.|  
|[CDataPathProperty::SetPath](#setpath)|Задает путь к свойству.|  
  
## <a name="remarks"></a>Примечания  
 Асинхронные свойства загружаются после синхронного запуска.  
  
 Класс `CDataPathProperty` является производным от **CAysncMonikerFile**. Для реализации асинхронных свойств элементов управления OLE, создайте класс, производный от `CDataPathProperty`и Переопределите [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable).  
  
 Дополнительные сведения о способах использования асинхронных моникеров и элементы управления ActiveX в веб-приложений см. в следующих статьях:  
  
- [Интернете первые шаги: Элементы управления ActiveX](../../mfc/activex-controls-on-the-internet.md)  
  
- [Интернете первые шаги: Асинхронные моникеры](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 `CDataPathProperty`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxctl.h  
  
##  <a name="cdatapathproperty"></a>  CDataPathProperty::CDataPathProperty  
 Создает объект `CDataPathProperty`.  
  
```  
CDataPathProperty(COleControl* pControl = NULL);  
CDataPathProperty(LPCTSTR lpszPath, COleControl* pControl = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pControl`  
 Указатель на объект элемента управления OLE следует связать с этим `CDataPathProperty` объекта.  
  
 `lpszPath`  
 Путь, который может быть абсолютным или относительным, используется для создания асинхронных моникер, ссылающийся на фактическое расположение абсолютный свойства. `CDataPathProperty` использует URL-адреса, не имена файлов. Если вы хотите `CDataPathProperty` объекта для файла, добавить `file://` в путь.  
  
### <a name="remarks"></a>Примечания  
 `COleControl` Объекта, на который указывает `pControl` используется **откройте** и получить производные классы. Если `pControl` — **NULL**, элемент управления, используемый с **откройте** следует задавать с `SetControl`. Если `lpszPath` — **NULL**, можно передать путь через **откройте** или установите его с `SetPath`.  
  
##  <a name="getcontrol"></a>  CDataPathProperty::GetControl  
 Вызовите эту функцию-член для извлечения `COleControl` объекта, связанного с `CDataPathProperty` объекта.  
  
```  
COleControl* GetControl();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на элемент управления OLE, связанный с `CDataPathProperty` объекта. **Значение NULL** Если управления не связан.  
  
##  <a name="getpath"></a>  CDataPathProperty::GetPath  
 Вызовите эту функцию-член для получения пути, устанавливается, когда `CDataPathProperty` объект был создан или указанные в **откройте**, или указанный в предыдущем вызове `SetPath` функции-члена.  
  
```  
CString GetPath() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает путь к самому свойству. Может быть пустым, если путь не был указан.  
  
##  <a name="open"></a>  CDataPathProperty::Open  
 Вызовите эту функцию-член для инициирования загрузку асинхронного свойства связанного элемента управления.  
  
```  
virtual BOOL Open(
    COleControl* pControl,  
    CFileException* pError = NULL);

 
virtual BOOL Open(
    LPCTSTR lpszPath,  
    COleControl* pControl,
    CFileException* pError = NULL);

 
virtual BOOL Open(
    LPCTSTR lpszPath,  
    CFileException* pError = NULL);  
  
virtual BOOL Open(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pControl`  
 Указатель на объект элемента управления OLE следует связать с этим `CDataPathProperty` объекта.  
  
 `pError`  
 Указатель на исключение файлов. В случае ошибки будет присвоено причину.  
  
 `lpszPath`  
 Путь, который может быть абсолютным или относительным, используется для создания асинхронных моникер, ссылающийся на фактическое расположение абсолютный свойства. `CDataPathProperty` использует URL-адреса, не имена файлов. Если вы хотите `CDataPathProperty` объекта для файла, добавить `file://` в путь.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Функция пытается получить `IBindHost` интерфейс из элемента управления.  
  
 Перед вызовом метода **откройте** без пути, необходимо задать значение для свойства пути. Это можно сделать, если объект является сконструированный, или путем вызова `SetPath` функции-члена.  
  
 Перед вызовом метода **откройте** без элемента управления, элемент управления ActiveX (ранее называвшиеся элемента управления OLE) могут быть связаны с объектом. Это можно сделать, если объект является сконструированный, или путем вызова `SetControl`.  
  
 Все перегрузки [CAsyncMonikerFile::Open](../../mfc/reference/casyncmonikerfile-class.md#open) также доступны из `CDataPathProperty`.  
  
##  <a name="resetdata"></a>  CDataPathProperty::ResetData  
 Эта функция вызывается для получения `CAsyncMonikerFile::OnDataAvailable` известить контейнера изменились свойства элемента управления, что все сведения, которые были загружены асинхронно не используется.  
  
```  
virtual void ResetData();
```  
  
### <a name="remarks"></a>Примечания  
 Открытие должен быть перезапущен. Производные классы могут переопределить эту функцию для различные значения по умолчанию.  
  
##  <a name="setcontrol"></a>  CDataPathProperty::SetControl  
 Вызовите эту функцию-член для связывания асинхронной элемента управления OLE с `CDataPathProperty` объекта.  
  
```  
void SetControl(COleControl* pControl);
```  
  
### <a name="parameters"></a>Параметры  
 `pControl`  
 Указатель на асинхронных управления OLE, связываемое со свойством.  
  
##  <a name="setpath"></a>  CDataPathProperty::SetPath  
 Вызовите эту функцию-член для задания пути свойства.  
  
```  
void SetPath(LPCTSTR lpszPath);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszPath`  
 Путь, который может быть абсолютным или относительным к свойству, загружаемых в асинхронном режиме. `CDataPathProperty` использует URL-адреса, не имена файлов. Если вы хотите `CDataPathProperty` объекта для файла, добавить `file://` в путь.  
  
## <a name="see-also"></a>См. также  
 [Изображение образца MFC](../../visual-cpp-samples.md)   
 [Класс CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)
