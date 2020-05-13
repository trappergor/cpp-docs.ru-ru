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
ms.openlocfilehash: 57ab463445f249b4e9393f19af103b7588962d5e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376999"
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
|[CAsyncMonikerFile::CAsyncMonikerFile](#casyncmonikerfile)|Формирует объект `CAsyncMonikerFile`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAsyncMonikerFile::Закрыть](#close)|Закрывает и высвобождает все ресурсы.|
|[CAsyncMonikerFile::GetBinding](#getbinding)|Извлекает указатель на асинхронную связывание передачи.|
|[CAsyncMonikerFile::GetFormatEtc](#getformatetc)|Извлекает формат данных в потоке.|
|[CAsyncMonikerFile::Открыто](#open)|Открывает файл асинхронно.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CAsyncMonikerFile::CreateBindStatusCallback](#createbindstatuscallback)|Создает объект COM, `IBindStatusCallback`который реализует.|
|[CAsyncMonikerFile::GetBindInfo](#getbindinfo)|Вызывается библиотекой системы OLE, чтобы запросить информацию о типе привязки, которая будет создана.|
|[CAsyncMonikerFile::GetPriority](#getpriority)|Вызывается библиотекой системы OLE, чтобы получить приоритет привязки.|
|[CAsyncMonikerFile::OnDataДоступно](#ondataavailable)|Вызывается для предоставления данных по мере их появления клиенту во время асинхронных операций связывания.|
|[CAsyncMonikerFile::OnLowResource](#onlowresource)|Вызывается, когда ресурсы низки.|
|[CAsyncMonikerFile::OnProgress](#onprogress)|Вызывается, чтобы указать прогресс в процессе загрузки данных.|
|[CAsyncMonikerFile::OnStartBinding](#onstartbinding)|Вызывается при запуске привязке.|
|[CAsyncMonikerFile::OnStopBinding](#onstopbinding)|Вызывается, когда асинхронная передача остановлена.|

## <a name="remarks"></a>Remarks

Полученные из [CMonikerFile](../../mfc/reference/cmonikerfile-class.md), который, в свою очередь, происходит от [COleStreamFile](../../mfc/reference/colestreamfile-class.md), `CAsyncMonikerFile` использует интерфейс [IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker) для доступа к любому потоку данных асинхронно, в том числе загрузка файлов асинхронно из URL. Файлы могут быть свойствами панака данных элементов управления ActiveX.

Асинхронные моникеры используются в основном в приложениях с поддержкой Интернета и управления ActiveX для обеспечения гибкого пользовательского интерфейса во время передачи файлов. Ярким примером этого является использование [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md) для предоставления асинхронных свойств для элементов управления ActiveX. Объект `CDataPathProperty` будет неоднократно получать обратный вызов, чтобы указать наличие новых данных в ходе длительного процесса обмена свойствами.

Для получения дополнительной информации о том, как использовать асинхронные кликеры и элементы управления ActiveX в интернет-приложениях, см.

- [Первые шаги Интернета: Асинхронные Моники](../../mfc/asynchronous-monikers-on-the-internet.md)

- [Первые шаги в Интернете: Управление ActiveX](../../mfc/activex-controls-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

`CAsyncMonikerFile`

## <a name="requirements"></a>Требования

**Заголовок:** afxole.h

## <a name="casyncmonikerfilecasyncmonikerfile"></a><a name="casyncmonikerfile"></a>CAsyncMonikerFile::CAsyncMonikerFile

Формирует объект `CAsyncMonikerFile`.

```
CAsyncMonikerFile();
```

### <a name="remarks"></a>Remarks

Он не создает `IBindHost` интерфейс. `IBindHost`используется только в том случае, если вы предоставляете его в функции `Open` члена.

Для описания интерфейса, `IBindHost` см.

## <a name="casyncmonikerfileclose"></a><a name="close"></a>CAsyncMonikerFile::Закрыть

Вызовите эту функцию, чтобы закрыть и высвободить все ресурсы.

```
virtual void Close();
```

### <a name="remarks"></a>Remarks

Можно вызвать неоткрытые или уже закрытые файлы.

## <a name="casyncmonikerfilecreatebindstatuscallback"></a><a name="createbindstatuscallback"></a>CAsyncMonikerFile::CreateBindStatusCallback

Создает объект COM, `IBindStatusCallback`который реализует.

```
virtual IUnknown* CreateBindStatusCallback(IUnknown* pUnkControlling);
```

### <a name="parameters"></a>Параметры

*pUnkКонтроль*<br/>
Указатель на элемент управления неизвестный `IUnknown`(внешний) или NULL, если агрегация не используется.

### <a name="return-value"></a>Возвращаемое значение

Если *pUnkControlling* не является NULL, функция возвращает `IUnknown` указатель на внутренний `IBindStatusCallback`на новый объект COM поддержки. Если `pUnkControlling` null, функция возвращает указатель `IUnknown` на новый объект `IBindStatusCallback`COM, поддерживающий.

### <a name="remarks"></a>Remarks

`CAsyncMonikerFile`требует объекта COM, `IBindStatusCallback`который реализует. МФЦ реализует такой объект, и он агрегируется. Вы можете `CreateBindStatusCallback` переопределить, чтобы вернуть свой собственный объект COM. Ваш объект COM может агрегировать `CreateBindStatusCallback` реализацию MFC, вызывая неизвестен ваш объект COM. Объекты COM, `CCmdTarget` реализованные с помощью поддержки COM, могут получить элемент управления, неизвестный с помощью. `CCmdTarget::GetControllingUnknown`

Кроме того, ваш объект COM может делегировать `CreateBindStatusCallback( NULL )`реализацию MFC, позвонив в систему.

[CAsyncMonikerFile::Открытые](#open) вызовы `CreateBindStatusCallback`.

Для получения дополнительной информации о асинхронных клиикерах и асинхронной привязке см. [IBindStatusCallback](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775060\(v=vs.85\)) [How Asynchronous Binding and Storage Work](/windows/win32/Stg/how-asynchronous-binding-and-storage-work) Для обсуждения агрегации [см.](/windows/win32/com/aggregation) Все три темы находятся в Windows SDK.

## <a name="casyncmonikerfilegetbindinfo"></a><a name="getbindinfo"></a>CAsyncMonikerFile::GetBindInfo

Позвонил от клиента асинхронного прозвища, чтобы рассказать асинхронному прозвищу, как он хочет связать.

```
virtual DWORD GetBindInfo() const;
```

### <a name="return-value"></a>Возвращаемое значение

Извлекает настройки `IBindStatusCallBack`для . Для описания интерфейса, `IBindStatusCallback` см.

### <a name="remarks"></a>Remarks

Реализация по умолчанию устанавливает привязку как асинхронную, использовать среду хранения (поток) и использовать модель нажатия данных. Переопределить эту функцию, если вы хотите изменить поведение привязки.

Одной из причин для этого было бы связывать с помощью модели вытягивания данных вместо модели нажатия данных. В модели вытягивания данных клиент управляет операцией связывания, а псевдоним предоставляет данные клиенту только при чтении. В модели нажатия данных кличка приводит к работе асинхронного связывания и постоянно уведомляет клиента при наличии новых данных.

## <a name="casyncmonikerfilegetbinding"></a><a name="getbinding"></a>CAsyncMonikerFile::GetBinding

Вызовите эту функцию, чтобы получить указатель на асинхронную связывание передачи.

```
IBinding* GetBinding() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `IBinding` интерфейс, предусмотренный при начале асинхронной передачи. Возвращает NULL, если по какой-либо причине передача не может быть осуществлена асинхронно.

### <a name="remarks"></a>Remarks

Это позволяет контролировать процесс передачи `IBinding` данных через интерфейс, например, с `IBinding::Abort`, `IBinding::Pause`и `IBinding::Resume`.

Для описания интерфейса, `IBinding` см.

## <a name="casyncmonikerfilegetformatetc"></a><a name="getformatetc"></a>CAsyncMonikerFile::GetFormatEtc

Вызовите эту функцию, чтобы получить формат данных в потоке.

```
FORMATETC* GetFormatEtc() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на структуру Windows [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) для открываемого в настоящее время потока. Возвращает NULL, если моникер не был связан, если он не асинхронный, или если асинхронная операция не началась.

## <a name="casyncmonikerfilegetpriority"></a><a name="getpriority"></a>CAsyncMonikerFile::GetPriority

Вызывается от клиента асинхронного прозвища, как обязательный процесс начинает получать приоритет, отданный потоку для связывающей операции.

```
virtual LONG GetPriority() const;
```

### <a name="return-value"></a>Возвращаемое значение

Приоритет, при котором будет происходить асинхронная передача. Один из стандартных флагов приоритета потока: THREAD_PRIORITY_ABOVE_NORMAL, THREAD_PRIORITY_BELOW_NORMAL, THREAD_PRIORITY_HIGHEST, THREAD_PRIORITY_IDLE, THREAD_PRIORITY_LOWEST, THREAD_PRIORITY_NORMAL и THREAD_PRIORITY_TIME_CRITICAL. Ознакомьтесь с функцией Windows [SetThreadPriority](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) для описания этих значений.

### <a name="remarks"></a>Remarks

`GetPriority`не следует называть напрямую. THREAD_PRIORITY_NORMAL возвращается по умолчанию.

## <a name="casyncmonikerfileondataavailable"></a><a name="ondataavailable"></a>CAsyncMonikerFile::OnDataДоступно

Асинхронное прозвище `OnDataAvailable` требует предоставления данных клиенту по мере его поступления во время асинхронных операций связывания.

```
virtual void OnDataAvailable(DWORD dwSize, DWORD bscfFlag);
```

### <a name="parameters"></a>Параметры

*dwSize*<br/>
Совокупное количество (в байтах) данных, доступных с начала связывания. Может быть равен нулю, что указывает на то, что объем данных не имеет отношения к операции, или что конкретная сумма не стала доступной.

*bscfФлаг*<br/>
Значение перечисления BSCF. Может быть одно или несколько из следующих значений:

- BSCF_FIRSTDATANOTIFICATION определяет первый `OnDataAvailable` вызов для данной операции связывания.

- BSCF_INTERMEDIATEDATANOTIFICATION идентифицирует вызов посредника `OnDataAvailable` для операции связывания.

- BSCF_LASTDATANOTIFICATION идентифицирует последний `OnDataAvailable` вызов для операции связывания.

### <a name="remarks"></a>Remarks

Реализация по умолчанию этой функции не выполняет никаких действий. Приведены следующие примеры для реализации выборки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWinInet#5](../../mfc/codesnippet/cpp/casyncmonikerfile-class_1.cpp)]

## <a name="casyncmonikerfileonlowresource"></a><a name="onlowresource"></a>CAsyncMonikerFile::OnLowResource

Вызывается по прозвищу, когда ресурсы низки.

```
virtual void OnLowResource();
```

### <a name="remarks"></a>Remarks

Вызовы реализации по `GetBinding( )-> Abort( )`умолчанию.

## <a name="casyncmonikerfileonprogress"></a><a name="onprogress"></a>CAsyncMonikerFile::OnProgress

Вызывается по прозвищу неоднократно, чтобы указать текущий ход этой операции связывания, как правило, с разумными интервалами во время длительной операции.

```
virtual void OnProgress(
    ULONG ulProgress,
    ULONG ulProgressMax,
    ULONG ulStatusCode,
    LPCTSTR szStatusText);
```

### <a name="parameters"></a>Параметры

*ulProgress*<br/>
Указывает текущий ход операции связывания относительно ожидаемого максимума, указанного в *ulProgressMax.*

*ulProgressMax*<br/>
Указывает ожидаемое максимальное значение *ulProgress* на `OnProgress` время вызовов для этой операции.

*ulStatusCode*<br/>
Предоставляет дополнительную информацию о ходе операции связывания. Допустимые значения взяты `BINDSTATUS` из перечисления. Возможные значения см. в разделе "Примечания".

*szStatusТекст*<br/>
Информация о текущем прогрессе, в зависимости от стоимости *ulStatusCode*. Возможные значения см. в разделе "Примечания".

### <a name="remarks"></a>Remarks

Возможные значения для *ulStatusCode* (и *szStatusText* для каждого значения) являются:

|||
|-|-|
|BINDSTATUS_FINDINGRESOURCE  |Операция связывания находит ресурс, который удерживает объект или хранилище. *SzStatusText* предоставляет имя отображения исцеляемого ресурса (например, "www.microsoft.com").  |
|BINDSTATUS_CONNECTING  |Операция связывания подключается к ресурсу, который удерживает объект или хранилище. *SzStatusText* предоставляет имя отображения связанного ресурса (например, IP-адрес).  |
|BINDSTATUS_SENDINGREQUEST|Операция связывания требует привязки объекта или хранилища. *SzStatusText* предоставляет имя отображения объекта (например, имя файла).|
|BINDSTATUS_REDIRECTING  |Операция связывания была перенаправлена в другое местоположение данных. *SzStatusText* предоставляет имя отображения нового местоположения данных.  |
|BINDSTATUS_USINGCACHEDCOPY  |Операция связывания - это извлечение запрашиваемого объекта или хранилища из кэшированной копии. *SzStatusText* является NULL.  |
|BINDSTATUS_BEGINDOWNLOADDATA  |Операция связывания начала получать объект или хранилище, которое должно быть привязано к. *SzStatusText* предоставляет имя отображения данных.|
|BINDSTATUS_DOWNLOADINGDATA  |Операция связывания продолжает получать объект или хранилище. *SzStatusText* предоставляет имя отображения данных.  |
|BINDSTATUS_ENDDOWNLOADDATA  |Операция связывания завершила прием объекта или хранилища. *SzStatusText* предоставляет имя отображения данных.  |
|BINDSTATUS_CLASSIDAVAILABLE  |Экземпляр объекта, который будет привязан к как раз вот-вот будет создан. *szStatusText* предоставляет CLSID нового объекта в формате строки, что позволяет клиенту при желании отменить операцию связывания.  |

## <a name="casyncmonikerfileonstartbinding"></a><a name="onstartbinding"></a>CAsyncMonikerFile::OnStartBinding

Переопределить эту функцию в выдвитом классе для выполнения действий при запуске связывания.

```
virtual void OnStartBinding();
```

### <a name="remarks"></a>Remarks

Эта функция называется обратно по прозвищу. Реализация по умолчанию не выполняет никаких действий.

## <a name="casyncmonikerfileonstopbinding"></a><a name="onstopbinding"></a>CAsyncMonikerFile::OnStopBinding

Вызывается по прозвищу в конце операции связывания.

```
virtual void OnStopBinding(HRESULT hresult, LPCTSTR szError);
```

### <a name="parameters"></a>Параметры

*Hresult*<br/>
HRESULT, который является значением ошибки или предупреждения.

*szErrort*<br/>
Строка символов, описывающая ошибку.

### <a name="remarks"></a>Remarks

Переопределить эту функцию для выполнения действий, когда передача остановлена. По умолчанию функция `IBinding`выпускает .

Для описания интерфейса, `IBinding` см.

## <a name="casyncmonikerfileopen"></a><a name="open"></a>CAsyncMonikerFile::Открыто

Вызов эту функцию участника, чтобы открыть файл асинхронно.

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
Указатель для файла, который будет открыт асинхронно. Файл может быть любым действительным URL или именем файла.

*pОшибка*<br/>
Указатель на исключения файлов. В случае ошибки, она будет установлена на причину.

*pMoniker*<br/>
Указатель на асинхронный интерфейс `IMoniker`моникера, точное прозвище, которое представляет собой комбинацию собственного `IOleClientSite::GetMoniker(OLEWHICHMK_CONTAINER)`прозвища документа, которое можно получить с помощью, и прозвище, созданное из имени пути. Элемент управления может использовать это прозвище для связывания, но это не то прозвище, которое должен сохранить элемент управления.

*pBindHost*<br/>
Указатель на `IBindHost` интерфейс, который будет использоваться для создания моникера из потенциально относительного имени пути. Если хост связывания является недействительным или не предоставляет псевдоним, вызов по умолчанию выполняется. `Open(lpszFileName,pError)` Для описания интерфейса, `IBindHost` см.

*pServiceProvider*<br/>
Указатель на интерфейс `IServiceProvider` . Если поставщик услуг является недействительным или не `IBindHost`предоставляет услугу для, вызов по `Open(lpszFileName,pError)`умолчанию.

*pНеизвестный*<br/>
Указатель на интерфейс `IUnknown` . Если `IServiceProvider` найдено, функция запрашивает `IBindHost`для . Если поставщик услуг является недействительным или не `IBindHost`предоставляет услугу для, вызов по `Open(lpszFileName,pError)`умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если файл успешно открыт; в противном случае 0.

### <a name="remarks"></a>Remarks

Этот вызов инициирует процесс связывания.

Для параметра *lpszURL* можно использовать URL или имя файла. Пример:

[!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/casyncmonikerfile-class_2.cpp)]

\- или -

[!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/casyncmonikerfile-class_3.cpp)]

## <a name="see-also"></a>См. также раздел

[Класс CMonikerFile](../../mfc/reference/cmonikerfile-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CMonikerFile](../../mfc/reference/cmonikerfile-class.md)<br/>
[Класс CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)
