---
title: Класс CAsyncMonikerFile
ms.date: 11/04/2016
f1_keywords:
- CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile::CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile::Close
- AFXOLE/CAsyncMonikerFile::GetBinding
- AFXOLE/CAsyncMonikerFile::GetFormatEtc
- AFXOLE/CAsyncMonikerFile::Open
- AFXOLE/CAsyncMonikerFile::CreateBindStatusCallback
- AFXOLE/CAsyncMonikerFile::GetBindInfo
- AFXOLE/CAsyncMonikerFile::GetPriority
- AFXOLE/CAsyncMonikerFile::OnDataAvailable
- AFXOLE/CAsyncMonikerFile::OnLowResource
- AFXOLE/CAsyncMonikerFile::OnProgress
- AFXOLE/CAsyncMonikerFile::OnStartBinding
- AFXOLE/CAsyncMonikerFile::OnStopBinding
helpviewer_keywords:
- CAsyncMonikerFile [MFC], CAsyncMonikerFile
- CAsyncMonikerFile [MFC], Close
- CAsyncMonikerFile [MFC], GetBinding
- CAsyncMonikerFile [MFC], GetFormatEtc
- CAsyncMonikerFile [MFC], Open
- CAsyncMonikerFile [MFC], CreateBindStatusCallback
- CAsyncMonikerFile [MFC], GetBindInfo
- CAsyncMonikerFile [MFC], GetPriority
- CAsyncMonikerFile [MFC], OnDataAvailable
- CAsyncMonikerFile [MFC], OnLowResource
- CAsyncMonikerFile [MFC], OnProgress
- CAsyncMonikerFile [MFC], OnStartBinding
- CAsyncMonikerFile [MFC], OnStopBinding
ms.assetid: 17378b66-a49a-4b67-88e3-7756ad26a2fc
ms.openlocfilehash: 107f791505bc41b8dbf9c0374c5e3821abbc0fe3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50669070"
---
# <a name="casyncmonikerfile-class"></a>Класс CAsyncMonikerFile

Предоставляет функции для использования асинхронных моникеров в элементах управления ActiveX (ранее элементах управления OLE).

## <a name="syntax"></a>Синтаксис

```
class CAsyncMonikerFile : public CMonikerFile
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAsyncMonikerFile::CAsyncMonikerFile](#casyncmonikerfile)|Создает объект `CAsyncMonikerFile`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAsyncMonikerFile::Close](#close)|Закрывает и освобождает все ресурсы.|
|[CAsyncMonikerFile::GetBinding](#getbinding)|Извлекает указатель на асинхронную передачу привязки.|
|[CAsyncMonikerFile::GetFormatEtc](#getformatetc)|Получает формат данных в потоке.|
|[CAsyncMonikerFile::Open](#open)|Открывает файл асинхронно.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CAsyncMonikerFile::CreateBindStatusCallback](#createbindstatuscallback)|Создает объект COM, который реализует `IBindStatusCallback`.|
|[CAsyncMonikerFile::GetBindInfo](#getbindinfo)|Вызывается библиотекой системы OLE для получения сведений о типа привязки должен быть создан.|
|[CAsyncMonikerFile::GetPriority](#getpriority)|Вызывается библиотекой системы OLE для получения приоритет привязки.|
|[CAsyncMonikerFile::OnDataAvailable](#ondataavailable)|Вызывается для предоставления данных, так как он становится доступным для клиента во время операций асинхронной привязки.|
|[CAsyncMonikerFile::OnLowResource](#onlowresource)|Вызывается, когда не хватает ресурсов.|
|[CAsyncMonikerFile::OnProgress](#onprogress)|Вызывается для отображения процесса скачивания данных.|
|[CAsyncMonikerFile::OnStartBinding](#onstartbinding)|Вызывается, когда начинается привязка.|
|[CAsyncMonikerFile::OnStopBinding](#onstopbinding)|Вызывается, когда асинхронная передача остановлена.|

## <a name="remarks"></a>Примечания

Производный от [CMonikerFile](../../mfc/reference/cmonikerfile-class.md), который в свою очередь является производным от [COleStreamFile](../../mfc/reference/colestreamfile-class.md), `CAsyncMonikerFile` использует [IMoniker](/windows/desktop/api/objidl/nn-objidl-imoniker) интерфейс для доступа к любой поток данных асинхронно включая асинхронную загрузку файлов из URL-адрес. Файлы могут быть свойства пути к данным элементов управления ActiveX.

Асинхронные моникеры используются главным образом в Интернет-приложений и элементов управления ActiveX для предоставления отклика пользовательского интерфейса во время передачи файлов. Хорошим примером этого является использование [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md) для предоставления асинхронного свойств для элементов управления ActiveX. `CDataPathProperty` Объекта несколько раз получит обратный вызов для указания доступности новых данных во время длительных свойство exchange.

Дополнительные сведения о способах использования асинхронных моникеров и элементы управления ActiveX в веб-приложений см. в разделе со следующими статьями:

- [Интернете первые шаги: Асинхронные моникеры](../../mfc/asynchronous-monikers-on-the-internet.md)

- [Интернете первые шаги: Элементы управления ActiveX](../../mfc/activex-controls-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

`CAsyncMonikerFile`

## <a name="requirements"></a>Требования

**Заголовок:** afxole.h

##  <a name="casyncmonikerfile"></a>  CAsyncMonikerFile::CAsyncMonikerFile

Создает объект `CAsyncMonikerFile`.

```
CAsyncMonikerFile();
```

### <a name="remarks"></a>Примечания

Он не создает `IBindHost` интерфейс. `IBindHost` используется только в том случае, если указать его в `Open` функция-член.

Описание `IBindHost` интерфейсом, см. в Windows SDK.

##  <a name="close"></a>  CAsyncMonikerFile::Close

Вызывайте эту функцию, чтобы закрыть и освободить все ресурсы.

```
virtual void Close();
```

### <a name="remarks"></a>Примечания

Может вызываться для файлов неоткрытый или уже закрыт.

##  <a name="createbindstatuscallback"></a>  CAsyncMonikerFile::CreateBindStatusCallback

Создает объект COM, который реализует `IBindStatusCallback`.

```
virtual IUnknown* CreateBindStatusCallback(IUnknown* pUnkControlling);
```

### <a name="parameters"></a>Параметры

*pUnkControlling*<br/>
Указатель на управляющий unknown (внешний `IUnknown`) или значение NULL, если не используется статистической обработки.

### <a name="return-value"></a>Возвращаемое значение

Если *pUnkControlling* не равно NULL, функция возвращает указатель на внутренний `IUnknown` на новый объект COM, поддерживающий `IBindStatusCallback`. Если `pUnkControlling` имеет значение NULL, функция возвращает указатель на `IUnknown` на новый объект COM, поддерживающий `IBindStatusCallback`.

### <a name="remarks"></a>Примечания

`CAsyncMonikerFile` требуется объект COM, реализующий `IBindStatusCallback`. MFC реализует такой объект, и это статистическое вычисление может выполняться. Можно переопределить `CreateBindStatusCallback` для возврата COM-объект. COM-объект может агрегировать реализации MFC путем вызова `CreateBindStatusCallback` с управляющий unknown COM-объекта. COM-объекты, реализованные с помощью `CCmdTarget` поддержки модели COM можно получить, управляющий Неизвестный с помощью `CCmdTarget::GetControllingUnknown`.

Кроме того, COM-объект можно делегировать реализацию MFC путем вызова `CreateBindStatusCallback( NULL )`.

[CAsyncMonikerFile::Open](#open) вызовы `CreateBindStatusCallback`.

Дополнительные сведения об асинхронных моникеров и асинхронной привязки см. в разделе [IBindStatusCallback](https://msdn.microsoft.com/library/ie/ms775060) интерфейс и [как асинхронной привязки и рабочего хранилища](/windows/desktop/Stg/how-asynchronous-binding-and-storage-work). Описание статистической обработки, см. в разделе [статистической обработки](/windows/desktop/com/aggregation). Все три раздела предназначены в пакете Windows SDK.

##  <a name="getbindinfo"></a>  CAsyncMonikerFile::GetBindInfo

Вызывается из клиенту асинхронным моникером сообщить асинхронный моникер, в том, как ему нужно привязать.

```
virtual DWORD GetBindInfo() const;
```

### <a name="return-value"></a>Возвращаемое значение

Извлекает параметры для `IBindStatusCallBack`. Описание `IBindStatusCallback` интерфейсом, см. в Windows SDK.

### <a name="remarks"></a>Примечания

Реализация по умолчанию задает привязку, чтобы асинхронными, для использования в среде хранения (поток) и использовать модель передачи данных. Переопределите эту функцию, если вы хотите изменить поведение привязки.

Одна из причин для этого следует осуществить привязку с помощью модели по запросу данных вместо модель принудительной отправки данных. В модели извлечения данных, то клиент управляет операция привязки и моникер только предоставляет данные клиенту при его чтении. В модели принудительной отправки данных моникер управляет операция асинхронной привязки и постоянно уведомляет клиента, когда новые данные будут доступны.

##  <a name="getbinding"></a>  CAsyncMonikerFile::GetBinding

Вызывайте эту функцию для получения указателя на асинхронную передачу привязки.

```
IBinding* GetBinding() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `IBinding` интерфейс, предоставляемый, когда начинается асинхронная передача. Возвращает значение NULL, если для какой-либо причине передачу невозможно асинхронно.

### <a name="remarks"></a>Примечания

Это позволяет контролировать процесс с помощью передачи данных `IBinding` интерфейса, например, с помощью `IBinding::Abort`, `IBinding::Pause`, и `IBinding::Resume`.

Описание `IBinding` интерфейсом, см. в Windows SDK.

##  <a name="getformatetc"></a>  CAsyncMonikerFile::GetFormatEtc

Вызывайте эту функцию для получения формат данных в потоке.

```
FORMATETC* GetFormatEtc() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на структуру Windows [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) открытое потока. Возвращает значение NULL, если моникер не привязан, если он не является асинхронным, или в том случае, если асинхронная операция не было начато.

##  <a name="getpriority"></a>  CAsyncMonikerFile::GetPriority

Вызывается из клиента асинхронным моникером начинает процесс привязки получают приоритет потока для операции привязки.

```
virtual LONG GetPriority() const;
```

### <a name="return-value"></a>Возвращаемое значение

Приоритет, по которому асинхронная передача будет выполняться. Один из флагов приоритет стандартных потоков: THREAD_PRIORITY_ABOVE_NORMAL, THREAD_PRIORITY_BELOW_NORMAL, THREAD_PRIORITY_HIGHEST, THREAD_PRIORITY_IDLE, наинизший, THREAD_PRIORITY_NORMAL и THREAD_PRIORITY_TIME_CRITICAL. См. в разделе Windows функция [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) описание из следующих значений.

### <a name="remarks"></a>Примечания

`GetPriority` не следует вызывать напрямую. THREAD_PRIORITY_NORMAL возвращается в реализации по умолчанию.

##  <a name="ondataavailable"></a>  CAsyncMonikerFile::OnDataAvailable

Вызывает асинхронным моникером `OnDataAvailable` для предоставления данных клиенту, так как она станет доступной, во время асинхронной привязки операции.

```
virtual void OnDataAvailable(DWORD dwSize, DWORD bscfFlag);
```

### <a name="parameters"></a>Параметры

*dwSize*<br/>
Совокупное объем (в байтах) данных, доступных с начала выполнения привязки. Может быть 0, указывающее, что объем данных, не имеет отношения к операции, или что не определенную сумму стала доступной.

*bscfFlag*<br/>
Значение перечисления BSCF. Может иметь одно или несколько из следующих значений:

- BSCF_FIRSTDATANOTIFICATION идентифицирует первый вызов `OnDataAvailable` для данной операции привязки.

- BSCF_INTERMEDIATEDATANOTIFICATION идентифицирует промежуточный вызов `OnDataAvailable` для операции привязки.

- BSCF_LASTDATANOTIFICATION идентифицирует последнего вызова `OnDataAvailable` для операции привязки.

### <a name="remarks"></a>Примечания

Реализация по умолчанию этой функции не выполняет никаких действий. См. приведенный ниже образец реализации.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWinInet#5](../../mfc/codesnippet/cpp/casyncmonikerfile-class_1.cpp)]

##  <a name="onlowresource"></a>  CAsyncMonikerFile::OnLowResource

Вызывается моникером, когда не хватает ресурсов.

```
virtual void OnLowResource();
```

### <a name="remarks"></a>Примечания

По умолчанию реализация вызывает `GetBinding( )-> Abort( )`.

##  <a name="onprogress"></a>  CAsyncMonikerFile::OnProgress

Вызывается специальным именем несколько раз, чтобы указать текущий ход выполнения этой операции привязки, обычно в разумные интервалы во время длительной операции.

```
virtual void OnProgress(
    ULONG ulProgress,
    ULONG ulProgressMax,
    ULONG ulStatusCode,
    LPCTSTR szStatusText);
```

### <a name="parameters"></a>Параметры

*ulProgress*<br/>
Указывает текущее положение привязки операции относительно ожидаемого максимума, указанного в *ulProgressMax*.

*ulProgressMax*<br/>
Указывает ожидаемое максимальное значение параметра *ulProgress* для длительности вызовов `OnProgress` для этой операции.

*ulStatusCode*<br/>
Дополнительные сведения о ходе выполнения операции привязки. Допустимые значения берутся из `BINDSTATUS` перечисления. См. в разделе "Примечания" для возможных значений.

*szStatusText*<br/>
Сведения о текущих, в зависимости от значения *ulStatusCode*. См. в разделе "Примечания" для возможных значений.

### <a name="remarks"></a>Примечания

Возможные значения для *ulStatusCode* (и *szStatusText* для каждого значения) являются:

|||
|-|-|
|BINDSTATUS_FINDINGRESOURCE  |Операция привязки находит ресурс, удерживающий объект или хранилище, которая привязывается к. *SzStatusText* предоставляет отображаемое имя ресурса, поиск которого для (например, «www.microsoft.com»).  |
|BINDSTATUS_CONNECTING  |Операция привязки соединяется с ресурсом, удерживающим объект или хранилище, которая привязывается к. *SzStatusText* предоставляет отображаемое имя ресурса подключения (например, IP-адресом).  |
|BINDSTATUS_SENDINGREQUEST|Операция привязки запрашивает объект или хранилище, которая привязывается к. *SzStatusText* предоставляет отображаемое имя объекта (например, имя файла).|
|BINDSTATUS_REDIRECTING  |Операция привязки был перенаправлен в другое расположение. *SzStatusText* предоставляет отображаемое имя нового расположения данных.  |
|BINDSTATUS_USINGCACHEDCOPY  |Операция привязки извлекает запрошенный объект или хранилище из кэшированной копии. *SzStatusText* имеет значение NULL.  |
|BINDSTATUS_BEGINDOWNLOADDATA  |Операция привязки начала получать объект или хранилище, которая привязывается к. *SzStatusText* предоставляет отображаемое имя расположения данных.|
|BINDSTATUS_DOWNLOADINGDATA  |Операция привязки продолжает получать объект или хранилище, которая привязывается к. *SzStatusText* предоставляет отображаемое имя расположения данных.  |
|BINDSTATUS_ENDDOWNLOADDATA  |Операция привязки закончила получать объект или хранилище, которая привязывается к. *SzStatusText* предоставляет отображаемое имя расположения данных.  |
|BINDSTATUS_CLASSIDAVAILABLE  |Экземпляр объекта, которая привязывается к собирается просто создать. *SzStatusText* предоставляет CLSID нового объекта в строковом формате, после чего клиент возможность отмены операции привязки, при необходимости.  |

##  <a name="onstartbinding"></a>  CAsyncMonikerFile::OnStartBinding

Переопределите эту функцию в производных классах для выполнения действий, когда начинается привязка.

```
virtual void OnStartBinding();
```

### <a name="remarks"></a>Примечания

Эта функция вызывается моникером. Реализация по умолчанию не выполняет никаких действий.

##  <a name="onstopbinding"></a>  CAsyncMonikerFile::OnStopBinding

Вызывается в конце операции привязки моникера.

```
virtual void OnStopBinding(HRESULT hresult, LPCTSTR szError);
```

### <a name="parameters"></a>Параметры

*hresult*<br/>
Значение HRESULT, ошибка или предупреждение значение.

*szErrort*<br/>
Строка описания ошибки.

### <a name="remarks"></a>Примечания

Переопределите эту функцию для выполнения действий, когда передача остановилась. По умолчанию функция освобождает `IBinding`.

Описание `IBinding` интерфейсом, см. в Windows SDK.

##  <a name="open"></a>  CAsyncMonikerFile::Open

Вызовите эта функция-член для открытия файла асинхронно.

```
virtual BOOL Open(
    LPCTSTR lpszURL,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszURL,
    IBindHost* pBindHost,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    IBindHost* pBindHost,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszURL,
    IServiceProvider* pServiceProvider,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    IServiceProvider* pServiceProvider,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszURL,
    IUnknown* pUnknown,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    IUnknown* pUnknown,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>Параметры

*lpszURL*<br/>
Указатель на файл, чтобы открыть асинхронно. Файл может быть любой допустимый URL-адрес или имя файла.

*pError*<br/>
Указатель на файл исключения. В случае ошибки он устанавливается на причину.

*pMoniker*<br/>
Указатель на интерфейс асинхронным моникером `IMoniker`, точный моникер, который представляет собой сочетание в собственной моникер документа, который можно получить с помощью `IOleClientSite::GetMoniker(OLEWHICHMK_CONTAINER)`и моникер, созданный из имени пути. Элемент управления можно использовать данный моникер для привязки, но это не моникер, который следует сохранить элемент управления.

*pBindHost*<br/>
Указатель на `IBindHost` интерфейс, который будет использоваться для создания моникера из потенциально относительного пути. Если привязки узла является недопустимым или не предоставляет моникер, вызов по умолчанию `Open(lpszFileName,pError)`. Описание `IBindHost` интерфейсом, см. в Windows SDK.

*pServiceProvider*<br/>
Указатель на `IServiceProvider` интерфейс. Если поставщик услуг, является недопустимым или не предоставляет службу для `IBindHost`, по умолчанию используется вызов `Open(lpszFileName,pError)`.

*pUnknown*<br/>
Указатель на `IUnknown` интерфейс. Если `IServiceProvider` найден, функция запрашивает `IBindHost`. Если поставщик услуг, является недопустимым или не предоставляет службу для `IBindHost`, по умолчанию используется вызов `Open(lpszFileName,pError)`.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если файл открыт успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот вызов запускает процесс привязки.

Можно использовать URL-адрес или имя файла для *lpszURL* параметра. Пример:

[!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/casyncmonikerfile-class_2.cpp)]

\- или -

[!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/casyncmonikerfile-class_3.cpp)]

## <a name="see-also"></a>См. также

[Класс CMonikerFile](../../mfc/reference/cmonikerfile-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CMonikerFile](../../mfc/reference/cmonikerfile-class.md)<br/>
[Класс CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)
