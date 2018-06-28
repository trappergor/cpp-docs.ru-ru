---
title: Класс CGopherFileFind | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CGopherFileFind
- AFXINET/CGopherFileFind
- AFXINET/CGopherFileFind::CGopherFileFind
- AFXINET/CGopherFileFind::FindFile
- AFXINET/CGopherFileFind::FindNextFile
- AFXINET/CGopherFileFind::GetCreationTime
- AFXINET/CGopherFileFind::GetLastAccessTime
- AFXINET/CGopherFileFind::GetLastWriteTime
- AFXINET/CGopherFileFind::GetLength
- AFXINET/CGopherFileFind::GetLocator
- AFXINET/CGopherFileFind::GetScreenName
- AFXINET/CGopherFileFind::IsDots
dev_langs:
- C++
helpviewer_keywords:
- CGopherFileFind [MFC], CGopherFileFind
- CGopherFileFind [MFC], FindFile
- CGopherFileFind [MFC], FindNextFile
- CGopherFileFind [MFC], GetCreationTime
- CGopherFileFind [MFC], GetLastAccessTime
- CGopherFileFind [MFC], GetLastWriteTime
- CGopherFileFind [MFC], GetLength
- CGopherFileFind [MFC], GetLocator
- CGopherFileFind [MFC], GetScreenName
- CGopherFileFind [MFC], IsDots
ms.assetid: 8465a979-6323-496d-ab4b-e81383fb999d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eae84c647f068e49136968e60bfd8bd51a528112
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2018
ms.locfileid: "37038533"
---
# <a name="cgopherfilefind-class"></a>Класс CGopherFileFind
Помогает в поиске файлов Интернета на серверах gopher.  
  
> [!NOTE]
>  Классы `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` и их члены являются устаревшими, так как они не работают на платформе Windows XP, но они будут продолжать работать на более старых платформ.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CGopherFileFind : public CFileFind  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CGopherFileFind::CGopherFileFind](#cgopherfilefind)|Создает объект `CGopherFileFind`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CGopherFileFind::FindFile](#findfile)|Поиск файла на сервере gopher.|  
|[CGopherFileFind::FindNextFile](#findnextfile)|Продолжает поиск файла из предыдущего вызова [FindFile](#findfile).|  
|[CGopherFileFind::GetCreationTime](#getcreationtime)|Возвращает время создания указанного файла.|  
|[CGopherFileFind::GetLastAccessTime](#getlastaccesstime)|Возвращает время последнего доступа к указанному файлу.|  
|[CGopherFileFind::GetLastWriteTime](#getlastwritetime)|Получает время последней записи в указанный файл.|  
|[CGopherFileFind::GetLength](#getlength)|Получает длину файла, в байтах.|  
|[CGopherFileFind::GetLocator](#getlocator)|Получение `CGopherLocator` объекта.|  
|[CGopherFileFind::GetScreenName](#getscreenname)|Возвращает имя экрана gopher.|  
|[CGopherFileFind::IsDots](#isdots)|Проверяет текущий каталог и родительский каталог маркеров во время итерации по файлам.|  
  
## <a name="remarks"></a>Примечания  
 `CGopherFileFind` включает функции-члены, начать поиск, найдите файл и файл URL-адрес возврата.  
  
 Другие классы MFC, предназначен для Интернета и поиск локального файла включают [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) и [CFileFind](../../mfc/reference/cfilefind-class.md). Вместе с `CGopherFileFind`, эти классы обеспечивают удобный механизм для пользователя найти определенные файлы, независимо от того, протокол сервера, тип файла или расположение (локальном компьютере или удаленном сервере.) Обратите внимание, что класс не MFC для поиска по HTTP-серверы HTTP поддерживает прямой файлами, необходимые для поиска.  
  
> [!NOTE]
> `CGopherFileFind` не поддерживает следующие функции-члены базового класса [CFileFind](../../mfc/reference/cfilefind-class.md):  
  
- [GetRoot](../../mfc/reference/cfilefind-class.md#getroot)  
  
- [GetFileName](../../mfc/reference/cfilefind-class.md#getfilename)  
  
- [GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath)  
  
- [GetFileTitle](../../mfc/reference/cfilefind-class.md#getfiletitle)  
  
- [GetFileURL](../../mfc/reference/cfilefind-class.md#getfileurl)  
  
 Кроме того, при использовании с `CGopherFileFind`, `CFileFind` функции-члена [IsDots](../../mfc/reference/cfilefind-class.md#isdots) всегда **FALSE**.  
  
 Дополнительные сведения об использовании `CGopherFileFind` и WinInet классов см. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFileFind](../../mfc/reference/cfilefind-class.md)  
  
 `CGopherFileFind`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxinet.h  
  
##  <a name="cgopherfilefind"></a>  CGopherFileFind::CGopherFileFind  
 Эта функция-член вызывается для создания `CGopherFileFind` объекта.  
  
```  
explicit CGopherFileFind(
    CGopherConnection* pConnection,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Параметры  
 *pConnection*  
 Указатель на [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) объекта.  
  
 *dwContext*  
 Идентификатор контекста для операции. В разделе **примечания** Дополнительные сведения о *dwContext*.  
  
### <a name="remarks"></a>Примечания  
 Значение по умолчанию для *dwContext* отправленных MFC, позволяющий `CGopherFileFind` объекта из [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта, который создан `CGopherFileFind` объекта. При построении `CGopherFileFind` объекта, можно переопределить значение по умолчанию для идентификатора контекста присвоено значение по своему выбору. Идентификатор контекста возвращается [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) показывают состояние для объекта, с помощью которого определяется. См. в статье [первые шаги в Интернете: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.  
  
##  <a name="findfile"></a>  CGopherFileFind::FindFile  
 Вызовите эту функцию-член для поиска файла gopher.  
  
```  
virtual BOOL FindFile(
    CGopherLocator& refLocator,  
    LPCTSTR pstrString,  
    DWORD dwFlags = INTERNET_FLAG_RELOAD);

 
virtual BOOL FindFile(
    LPCTSTR pstrString,  
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```  
  
### <a name="parameters"></a>Параметры  
 *refLocator*  
 Ссылку на [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) объекта.  
  
 *pstrString*  
 Указатель на строку, содержащую имя файла.  
  
 *dwFlags*  
 Флаги, описывающие способ обработки этого сеанса. Ниже приведены допустимые флаги.  
  
-   INTERNET_FLAG_RELOAD получить данные с удаленного сервера, даже если он кэшируется локально.  
  
-   INTERNET_FLAG_DONT_CACHE не кэшировать данные, локально или в всех шлюзов.  
  
-   Запрос INTERNET_FLAG_SECURE защиты транзакций в сети с помощью протокола SSL или использованию PCT. Этот флаг применим только для HTTP-запросов.  
  
-   INTERNET_FLAG_USE_EXISTING, если возможно, повторно использовать существующие подключения к серверу для новых **FindFile** запросов, а не создавать новый сеанс для каждого запроса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Чтобы получить расширенные сведения об ошибке, вызовите функцию Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Примечания  
 После вызова метода **FindFile** для получения первого объекта gopher, можно вызвать [FindNextFile](#findnextfile) для получения файлов последующих gopher.  
  
##  <a name="findnextfile"></a>  CGopherFileFind::FindNextFile  
 Вызовите эту функцию-член для продолжения поиска файла начался вызовом [CGopherFileFind::FindFile](#findfile).  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если имеется несколько файлов; нуль, если найден файл является последним элементом в каталоге или произошла ошибка. Чтобы получить расширенные сведения об ошибке, вызовите функцию Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360). Если найден файл последний файл в каталоге, или если соответствующие файлы можно найти, `GetLastError` функция возвращает ERROR_NO_MORE_FILES.  
  
##  <a name="getcreationtime"></a>  CGopherFileFind::GetCreationTime  
 Возвращает время создания текущего файла.  
  
```  
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetCreationTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *pTimeStamp*  
 Указатель на [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) структуру, содержащую время создания файла.  
  
 *refTime*  
 Ссылку на [CTime](../../atl-mfc-shared/reference/ctime-class.md) объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно; 0, если операция завершилась неудачей. `GetCreationTime` Возвращает 0 только в том случае, если [FindNextFile](#findnextfile) никогда не был вызван для этого `CGopherFileFind` объекта.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `GetCreationTime`.  
  
> [!NOTE]
>  Не все файловые системы для реализации отметку времени, возвращаемое этой функцией, используйте ту же семантику. Эта функция может возвращать то же значение, возвращенное функцией другие функции отметки времени, если базовой файловой системы или сервер не поддерживает сохранение атрибутов времени. В разделе [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структура сведения о форматах времени. В некоторых операционных системах возвращаемое значение времени — времени, были локальной зоны на компьютере, он находится. В разделе Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API-Интерфейс для получения дополнительной информации.  
  
##  <a name="getlastaccesstime"></a>  CGopherFileFind::GetLastAccessTime  
 Возвращает время последнего доступа к указанному файлу.  
  
```  
virtual BOOL GetLastAccessTime(CTime& refTime) const;  
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *refTime*  
 Ссылку на [CTime](../../atl-mfc-shared/reference/ctime-class.md) объекта.  
  
 *pTimeStamp*  
 Указатель на [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) структуру, содержащую время последнего доступа к файлу.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно; 0, если операция завершилась неудачей. `GetLastAccessTime` Возвращает 0 только в том случае, если [FindNextFile](#findnextfile) никогда не был вызван для этого `CGopherFileFind` объекта.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `GetLastAccessTime`.  
  
> [!NOTE]
>  Не все файловые системы для реализации отметку времени, возвращаемое этой функцией, используйте ту же семантику. Эта функция может возвращать то же значение, возвращенное функцией другие функции отметки времени, если базовой файловой системы или сервер не поддерживает сохранение атрибутов времени. В разделе [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структура сведения о форматах времени. В некоторых операционных системах возвращаемое значение времени — времени, были локальной зоны на компьютере, он находится. В разделе Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API-Интерфейс для получения дополнительной информации.  
  
##  <a name="getlastwritetime"></a>  CGopherFileFind::GetLastWriteTime  
 Возвращает время последнего изменения файла.  
  
```  
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetLastWriteTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *pTimeStamp*  
 Указатель на [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) структуру, содержащую время последней операции записи файла.  
  
 *refTime*  
 Ссылку на [CTime](../../atl-mfc-shared/reference/ctime-class.md) объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно; 0, если операция завершилась неудачей. `GetLastWriteTime` Возвращает 0 только в том случае, если [FindNextFile](#findnextfile) никогда не был вызван для этого `CGopherFileFind` объекта.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `GetLastWriteTime`.  
  
> [!NOTE]
>  Не все файловые системы для реализации отметку времени, возвращаемое этой функцией, используйте ту же семантику. Эта функция может возвращать то же значение, возвращенное функцией другие функции отметки времени, если базовой файловой системы или сервер не поддерживает сохранение атрибутов времени. В разделе [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структура сведения о форматах времени. В некоторых операционных системах возвращаемое значение времени — времени, были локальной зоны на компьютере, он находится. В разделе Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API-Интерфейс для получения дополнительной информации.  
  
##  <a name="getlength"></a>  CGopherFileFind::GetLength  
 Вызовите эту функцию-член для получения длину в байтах, найденного файла.  
  
```  
virtual ULONGLONG GetLength() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина найденного файла в байтах.  
  
### <a name="remarks"></a>Примечания  
 `GetLength` используется структура Win32 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) необходимо получить значение размера файла в байтах.  
  
> [!NOTE]
>  Начиная с MFC 7.0 `GetLength` поддерживает 64-разрядного целого типа. Ранее существовавшие кода, созданного с помощью этой новой версии библиотеки может привести к предупреждениям усечение.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CFile::GetLength](../../mfc/reference/cfile-class.md#getlength) (реализацию базового класса).  
  
##  <a name="getlocator"></a>  CGopherFileFind::GetLocator  
 Вызовите эту функцию-член для получения [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) объекта, [FindFile](#findfile) использует для поиска файла gopher.  
  
```  
CGopherLocator GetLocator() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CGopherLocator`.  
  
##  <a name="getscreenname"></a>  CGopherFileFind::GetScreenName  
 Вызовите эту функцию-член для получения имени экрана gopher.  
  
```  
CString GetScreenName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя экрана gopher.  
  
##  <a name="isdots"></a>  CGopherFileFind::IsDots  
 Проверяет текущий каталог и родительский каталог маркеров во время итерации по файлам.  
  
```  
virtual BOOL IsDots() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если найден файл имеет имя «. «или»..», указывающая, что найденный файл — это каталог. В противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `IsDots`.  
  
## <a name="see-also"></a>См. также  
 [Класс CFileFind](../../mfc/reference/cfilefind-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)   
 [Класс CFileFind](../../mfc/reference/cfilefind-class.md)   
 [Класс классе CInternetFile](../../mfc/reference/cinternetfile-class.md)   
 [Класс CGopherFile](../../mfc/reference/cgopherfile-class.md)   
 [Класс CHttpFile](../../mfc/reference/chttpfile-class.md)
