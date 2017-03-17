---
title: "Класс CDataPathProperty | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- ActiveX controls [C++], asynchronous
- OLE controls [C++], asynchronous
- CDataPathProperty class
- asynchronous controls [C++]
ms.assetid: 1f96efdb-54e4-460b-862c-eba5d4103488
caps.latest.revision: 24
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
ms.openlocfilehash: d767cf950d8b86959aadc2fd4d77401134a6dc75
ms.lasthandoff: 02/24/2017

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
|[CDataPathProperty::GetControl](#getcontrol)|Извлекает асинхронного управления OLE, связанного с `CDataPathProperty` объекта.|  
|[CDataPathProperty::GetPath](#getpath)|Получает путь к свойству.|  
|[CDataPathProperty::Open](#open)|Инициирует загрузку асинхронного свойства связанного элемента управления ActiveX (OLE).|  
|[CDataPathProperty::ResetData](#resetdata)|Вызывает `CAsyncMonikerFile::OnDataAvailable` для уведомления контейнер, в котором были изменены свойства элемента управления.|  
|[CDataPathProperty::SetControl](#setcontrol)|Задает асинхронный элемент управления ActiveX (OLE), связанное с этим свойством.|  
|[CDataPathProperty::SetPath](#setpath)|Задает путь к свойству.|  
  
## <a name="remarks"></a>Примечания  
 Асинхронные свойства загружаются после синхронного запуска.  
  
 Класс `CDataPathProperty` является производным от **CAysncMonikerFile**. Для реализации асинхронных свойств элементов управления OLE, создайте класс, производный от `CDataPathProperty`и Переопределите [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable).  
  
 Дополнительные сведения о способах использования асинхронных моникеров и элементы управления ActiveX в веб-приложений см. следующие статьи:  
  
- [Интернете первые шаги: Элементы управления ActiveX](../../mfc/activex-controls-on-the-internet.md)  
  
- [Internet первые шаги: Асинхронные моникеры](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 `CDataPathProperty`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxctl.h  
  
##  <a name="cdatapathproperty"></a>CDataPathProperty::CDataPathProperty  
 Создает объект `CDataPathProperty`.  
  
```  
CDataPathProperty(COleControl* pControl = NULL);  
CDataPathProperty(LPCTSTR lpszPath, COleControl* pControl = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pControl`  
 Указатель на объект элемента управления OLE, сопоставляемое с этим `CDataPathProperty` объекта.  
  
 `lpszPath`  
 Путь, который может быть абсолютным или относительным, используется для создания асинхронных моникер, ссылающийся на фактическое расположение абсолютный свойства. `CDataPathProperty`использует URL-адреса, не имена файлов. Если вы хотите `CDataPathProperty` объекта для файла, начало `file://` пути.  
  
### <a name="remarks"></a>Примечания  
 `COleControl` Объекта, на который указывает `pControl` используется **откройте** и получить производными классами. Если `pControl` — **NULL**, элемент управления, используемый с **откройте** должно быть задано значение `SetControl`. Если `lpszPath` — **NULL**, можно передать путь через **откройте** или настроить ее с помощью `SetPath`.  
  
##  <a name="getcontrol"></a>CDataPathProperty::GetControl  
 Вызовите эту функцию-член для получения `COleControl` объекта, связанного с `CDataPathProperty` объекта.  
  
```  
COleControl* GetControl();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на элемент управления OLE, связанных с `CDataPathProperty` объекта. **NULL** Если управления не связан.  
  
##  <a name="getpath"></a>CDataPathProperty::GetPath  
 Вызов этой функции-члена для получения пути, устанавливается, когда `CDataPathProperty` объект был создан или указанные в **откройте**, или указанный в предыдущем вызове `SetPath` функции-члена.  
  
```  
CString GetPath() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает путь к самому свойству. Может быть пустым, если путь не был указан.  
  
##  <a name="open"></a>CDataPathProperty::Open  
 Вызовите эту функцию-член, чтобы инициировать загрузку асинхронного свойства связанного элемента управления.  
  
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
 Указатель на объект элемента управления OLE, сопоставляемое с этим `CDataPathProperty` объекта.  
  
 `pError`  
 Указатель на исключение файлов. В случае возникновения ошибки будут устанавливаться на причину.  
  
 `lpszPath`  
 Путь, который может быть абсолютным или относительным, используется для создания асинхронных моникер, ссылающийся на фактическое расположение абсолютный свойства. `CDataPathProperty`использует URL-адреса, не имена файлов. Если вы хотите `CDataPathProperty` объекта для файла, начало `file://` пути.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Функция пытается получить `IBindHost` интерфейса из элемента управления.  
  
 Перед вызовом метода **откройте** без пути, необходимо задать значение для свойства пути. Это можно сделать, если объект является сконструированный, или путем вызова `SetPath` функции-члена.  
  
 Перед вызовом метода **откройте** без элемента управления может быть связан с объектом элемента управления ActiveX (ранее известный как элемент управления OLE). Это можно сделать, если объект является сконструированный, или путем вызова `SetControl`.  
  
 Все перегрузки [CAsyncMonikerFile::Open](../../mfc/reference/casyncmonikerfile-class.md#open) также доступны из `CDataPathProperty`.  
  
##  <a name="resetdata"></a>CDataPathProperty::ResetData  
 Эта функция вызывается для получения `CAsyncMonikerFile::OnDataAvailable` для уведомления контейнера изменились свойства элемента управления, что все сведения, загрузить асинхронно не используется.  
  
```  
virtual void ResetData();
```  
  
### <a name="remarks"></a>Примечания  
 Открытие следует перезапустить. Производные классы могут переопределять эту функцию для различные значения по умолчанию.  
  
##  <a name="setcontrol"></a>CDataPathProperty::SetControl  
 Вызовите эту функцию-член, чтобы связать элемент управления асинхронной OLE с `CDataPathProperty` объекта.  
  
```  
void SetControl(COleControl* pControl);
```  
  
### <a name="parameters"></a>Параметры  
 `pControl`  
 Указатель для управления асинхронной OLE, сопоставляемое со свойством.  
  
##  <a name="setpath"></a>CDataPathProperty::SetPath  
 Вызовите эту функцию-член, чтобы задать путь к свойству.  
  
```  
void SetPath(LPCTSTR lpszPath);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszPath`  
 Путь, который может быть абсолютным или относительным к свойству загружается асинхронно. `CDataPathProperty`использует URL-адреса, не имена файлов. Если вы хотите `CDataPathProperty` объекта для файла, начало `file://` пути.  
  
## <a name="see-also"></a>См. также  
 [Изображение примера MFC](../../visual-cpp-samples.md)   
 [Класс CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)

