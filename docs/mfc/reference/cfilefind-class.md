---
title: Класс CFileFind | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFileFind
- AFX/CFileFind
- AFX/CFileFind::CFileFind
- AFX/CFileFind::Close
- AFX/CFileFind::FindFile
- AFX/CFileFind::FindNextFile
- AFX/CFileFind::GetCreationTime
- AFX/CFileFind::GetFileName
- AFX/CFileFind::GetFilePath
- AFX/CFileFind::GetFileTitle
- AFX/CFileFind::GetFileURL
- AFX/CFileFind::GetLastAccessTime
- AFX/CFileFind::GetLastWriteTime
- AFX/CFileFind::GetLength
- AFX/CFileFind::GetRoot
- AFX/CFileFind::IsArchived
- AFX/CFileFind::IsCompressed
- AFX/CFileFind::IsDirectory
- AFX/CFileFind::IsDots
- AFX/CFileFind::IsHidden
- AFX/CFileFind::IsNormal
- AFX/CFileFind::IsReadOnly
- AFX/CFileFind::IsSystem
- AFX/CFileFind::IsTemporary
- AFX/CFileFind::MatchesMask
- AFX/CFileFind::CloseContext
- AFX/CFileFind::m_pTM
dev_langs:
- C++
helpviewer_keywords:
- CFileFind [MFC], CFileFind
- CFileFind [MFC], Close
- CFileFind [MFC], FindFile
- CFileFind [MFC], FindNextFile
- CFileFind [MFC], GetCreationTime
- CFileFind [MFC], GetFileName
- CFileFind [MFC], GetFilePath
- CFileFind [MFC], GetFileTitle
- CFileFind [MFC], GetFileURL
- CFileFind [MFC], GetLastAccessTime
- CFileFind [MFC], GetLastWriteTime
- CFileFind [MFC], GetLength
- CFileFind [MFC], GetRoot
- CFileFind [MFC], IsArchived
- CFileFind [MFC], IsCompressed
- CFileFind [MFC], IsDirectory
- CFileFind [MFC], IsDots
- CFileFind [MFC], IsHidden
- CFileFind [MFC], IsNormal
- CFileFind [MFC], IsReadOnly
- CFileFind [MFC], IsSystem
- CFileFind [MFC], IsTemporary
- CFileFind [MFC], MatchesMask
- CFileFind [MFC], CloseContext
- CFileFind [MFC], m_pTM
ms.assetid: 9990068c-b023-4114-9580-a50182d15240
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 82639ff7d4c4f6c6e33778b47509a2744cb12f13
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37337399"
---
# <a name="cfilefind-class"></a>Класс CFileFind
Выполняет поиск локального файла и является базовым классом для [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) и [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md), которые выполняют поиск файлов Интернета.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CFileFind : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CFileFind::CFileFind](#cfilefind)|Создает объект `CFileFind`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CFileFind::Close](#close)|Закрывает этот запрос поиска.|  
|[CFileFind::FindFile](#findfile)|Осуществляет поиск указанного имени файла в каталоге.|  
|[CFileFind::FindNextFile](#findnextfile)|Продолжает поиск файла из предыдущего вызова [FindFile](#findfile).|  
|[CFileFind::GetCreationTime](#getcreationtime)|Получает время создания файла.|  
|[CFileFind::GetFileName](#getfilename)|Возвращает имя, включая расширение файла|  
|[CFileFind::GetFilePath](#getfilepath)|Получает полный путь файла.|  
|[CFileFind::GetFileTitle](#getfiletitle)|Возвращает название найденного файла. Заголовок не включает расширение.|  
|[CFileFind::GetFileURL](#getfileurl)|Получает URL-адрес, включая путь к файлу, найденного файла.|  
|[CFileFind::GetLastAccessTime](#getlastaccesstime)|Получает время последнего доступа к файлу.|  
|[CFileFind::GetLastWriteTime](#getlastwritetime)|Получает время последнего данный файл был изменен и сохранен.|  
|[CFileFind::GetLength](#getlength)|Получает длину файла, в байтах.|  
|[CFileFind::GetRoot](#getroot)|Возвращает корневой каталог файла.|  
|[CFileFind::IsArchived](#isarchived)|Определяет, если выполняется архивирование найденного файла.|  
|[CFileFind::IsCompressed](#iscompressed)|Определяет, если найден файл сжат.|  
|[CFileFind::IsDirectory](#isdirectory)|Определяет, является ли найденного файла каталога.|  
|[CFileFind::IsDots](#isdots)|Определяет, имеет ли имя найденного файла имя «. «или»..», означает, что является папкой.|  
|[CFileFind::IsHidden](#ishidden)|Определяет, является ли скрытым найденного файла.|  
|[CFileFind::IsNormal](#isnormal)|Определяет, если найден файл является обычным (другими словами, не имеет других атрибутов).|  
|[CFileFind::IsReadOnly](#isreadonly)|Определяет, является ли найденного файла только для чтения.|  
|[CFileFind::IsSystem](#issystem)|Определяет, если найден файл является системным файлом.|  
|[CFileFind::IsTemporary](#istemporary)|Определяет, если найден файл является временным.|  
|[CFileFind::MatchesMask](#matchesmask)|Указывает атрибуты файла, чтобы найти нужный файл.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CFileFind::CloseContext](#closecontext)|Закрывает файл, указанный параметром текущий дескриптор поиска.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CFileFind::m_pTM](#m_ptm)|Указатель на `CAtlTransactionManager` объект.|  
  
## <a name="remarks"></a>Примечания  
 `CFileFind` включает в себя функции-члены, начать поиск, найдите файл и получить название, имя или путь к файлу. Для поиска в Интернете, функция-член [GetFileURL](#getfileurl) возвращает URL-адрес файла.  
  
 `CFileFind` базовый класс для двух других классов MFC предназначен для поиска конкретного сервера типов: `CGopherFileFind` предназначен для работы с серверами gopher и `CFtpFileFind` предназначен для работы с FTP-серверами. Вместе эти три класса предоставляют простой механизм для клиента для поиска файлов, независимо от того, протокол сервера, тип файла или расположение, на локальном компьютере или удаленном сервере.  
  
 Следующий код перечисляет все файлы в текущем каталоге, выводит имя каждого файла:  
  
 [!code-cpp[NVC_MFCFiles#31](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_1.cpp)]  
  
 Для простоты в примере, этот код использует стандартную библиотеку C++ `cout` класса. `cout` Строки можно заменить на вызов `CListBox::AddString`, например, в приложении с помощью графического интерфейса.  
  
 Дополнительные сведения об использовании `CFileFind` и другие классы WinInet, см. в статье [Internet программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CFileFind`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="cfilefind"></a>  CFileFind::CFileFind  
 Эта функция-член вызывается, когда `CFileFind` создания объекта.  
  
```  
CFileFind();  
CFileFind(CAtlTransactionManager* pTM);
```  
  
### <a name="parameters"></a>Параметры  
 *pTM*  
 Указатель на объект CAtlTransactionManager.  
  
### <a name="example"></a>Пример  
  См. в примере [CFileFind::GetFileName](#getfilename).  
  
##  <a name="close"></a>  CFileFind::Close  
 Эта функция члена завершить поиск, сброса контекста и освободить все ресурсы.  
  
```  
void Close();
```  
  
### <a name="remarks"></a>Примечания  
 После вызова метода `Close`, необходимо создать новый `CFileFind` экземпляра перед вызовом [FindFile](#findfile) чтобы начать новый поиск.  
  
### <a name="example"></a>Пример  
  См. в примере [CFileFind::GetFileName](#getfilename).  
  
##  <a name="closecontext"></a>  CFileFind::CloseContext  
 Закрывает файл, указанный параметром текущий дескриптор поиска.  
  
```  
virtual void CloseContext();
```  
  
### <a name="remarks"></a>Примечания  
 Закрывает файл, указанный дескриптор поиска текущее значение. Переопределите эту функцию, чтобы изменить поведение по умолчанию.  
  
 Необходимо вызвать [FindFile](#findfile) или [FindNextFile](#findnextfile) функции по крайней мере один раз для получения дескриптора допустимым поиска. `FindFile` И `FindNextFile` функции используют дескриптор поиска, чтобы найти файлы с именами, совпадающими с заданным именем.  
  
##  <a name="findfile"></a>  CFileFind::FindFile  
 Вызывайте эту функцию члена для поиска файла откройте.  
  
```  
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,  
    DWORD dwUnused = 0);
```  
  
### <a name="parameters"></a>Параметры  
 *pstrName*  
 Указатель на строку, содержащую имя файла для поиска. Если передается значение NULL *pstrName*, `FindFile` подстановочный знак (*.\*) поиска.  
  
 *dwUnused*  
 Зарезервированные, чтобы сделать `FindFile` полиморфным производных классов. Должно быть 0.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Чтобы получить расширенные сведения об ошибке, вызовите функцию Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Примечания  
 После вызова метода `FindFile` для начала поиска файла, вызовите [FindNextFile](#findnextfile) для извлечения последующих файлов. Необходимо вызвать `FindNextFile` по крайней мере один раз перед вызовом любой из следующих атрибутов функции-члены:  
  
- [GetCreationTime](#getcreationtime)  
  
- [GetFileName](#getfilename)  
  
- [GetFileTitle](#getfiletitle)  
  
- [GetFilePath](#getfilepath)  
  
- [GetFileURL](#getfileurl)  
  
- [GetLastAccessTime](#getlastaccesstime)  
  
- [GetLastWriteTime](#getlastwritetime)  
  
- [GetLength](#getlength)  
  
- [GetRoot](#getroot)  
  
- [IsArchived](#isarchived)  
  
- [IsCompressed](#iscompressed)  
  
- [IsDirectory](#isdirectory)  
  
- [IsDots](#isdots)  
  
- [IsHidden](#ishidden)  
  
- [IsNormal](#isnormal)  
  
- [IsReadOnly](#isreadonly)  
  
- [IsSystem](#issystem)  
  
- [IsTemporary](#istemporary)  
  
- [MatchesMask](#matchesmask)  
  
### <a name="example"></a>Пример  
  См. в примере [CFileFind::IsDirectory](#isdirectory).  
  
##  <a name="findnextfile"></a>  CFileFind::FindNextFile  
 Вызовите эту функцию-член для продолжения поиска файла из предыдущего вызова [FindFile](#findfile).  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, при наличии нескольких файлов; нуль, если найден файл является последним в каталоге или если возникает ошибка. Чтобы получить расширенные сведения об ошибке, вызовите функцию Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360). Если файл найден последнего файла в каталоге, или если соответствующие файлы можно найти, `GetLastError` функция возвращает ERROR_NO_MORE_FILES.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать `FindNextFile` по крайней мере один раз перед вызовом любой из следующих атрибутов функции-члены:  
  
- [GetCreationTime](#getcreationtime)  
  
- [GetFileName](#getfilename)  
  
- [GetFileTitle](#getfiletitle)  
  
- [GetFilePath](#getfilepath)  
  
- [GetFileURL](#getfileurl)  
  
- [GetLastAccessTime](#getlastaccesstime)  
  
- [GetLastWriteTime](#getlastwritetime)  
  
- [GetLength](#getlength)  
  
- [GetRoot](#getroot)  
  
- [IsArchived](#isarchived)  
  
- [IsCompressed](#iscompressed)  
  
- [IsDirectory](#isdirectory)  
  
- [IsDots](#isdots)  
  
- [IsHidden](#ishidden)  
  
- [IsNormal](#isnormal)  
  
- [IsReadOnly](#isreadonly)  
  
- [IsSystem](#issystem)  
  
- [IsTemporary](#istemporary)  
  
- [MatchesMask](#matchesmask)  
  
 `FindNextFile` Создает оболочку для функции Win32 [FindNextFile](http://msdn.microsoft.com/library/windows/desktop/aa364428).  
  
### <a name="example"></a>Пример  
  См. в примере [CFileFind::IsDirectory](#isdirectory).  
  
##  <a name="getcreationtime"></a>  CFileFind::GetCreationTime  
 Вызывайте эту функцию члена, чтобы получить время создания указанного файла.  
  
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
 Ненулевое значение, если выполнение прошло успешно; 0, если операция завершилась неудачей. `GetCreationTime` Возвращает 0 только в том случае, если [FindNextFile](#findnextfile) никогда не был вызван на это `CFileFind` объекта.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `GetCreationTime`.  
  
> [!NOTE]
>  Не все файловые системы используйте ту же семантику, чтобы реализовать отметку времени, возвращаемое этой функцией. Эта функция может возвращать же значение, возвращенное другие функции отметку времени, если базовой файловой системы или сервер не поддерживает сохранение атрибут времени. См. в разделе [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структура сведения о форматах времени. В некоторых операционных системах возвращаемое значение времени — времени, были зоны локальной машине, что он находится. См. в разделе Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API Дополнительные сведения.  
  
### <a name="example"></a>Пример  
  См. в примере [CFileFind::GetLength](#getlength).  
  
##  <a name="getfilename"></a>  CFileFind::GetFileName  
 Вызывайте эту функцию члена, чтобы получить имя файла.  
  
```  
virtual CString GetFileName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя файла недавно было обнаружено.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом GetFileName.  
  
 `GetFileName` является одним из трех `CFileFind` функции-члены, которые возвращают определенные виды имя файла. Ниже перечислены три и как они изменяются.  
  
- `GetFileName` Возвращает имя файла, включая расширение. Например, вызов `GetFileName` создать пользователя сообщение о файле *c:\myhtml\myfile.txt* возвращает имя файла *myfile.txt*.  
  
- [GetFilePath](#getfilepath) возвращает полный путь к файлу. Например, вызов `GetFilePath` создать пользователя сообщение о файле *c:\myhtml\myfile.txt* возвращает путь к файлу *c:\myhtml\myfile.txt*.  
  
- [GetFileTitle](#getfiletitle) возвращает имя файла без расширения файла. Например, вызов `GetFileTitle` создать пользователя сообщение о файле *c:\myhtml\myfile.txt* возвращает заголовок файла *myfile*.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#32](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_2.cpp)]  
  
##  <a name="getfilepath"></a>  CFileFind::GetFilePath  
 Вызывайте эту функцию члена, чтобы получить полный путь к указанному файлу.  
  
```  
virtual CString GetFilePath() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Путь к указанному файлу.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `GetFilePath`.  
  
 `GetFilePath` является одним из трех `CFileFind` функции-члены, которые возвращают определенные виды имя файла. Ниже перечислены три и как они изменяются.  
  
- [GetFileName](#getfilename) возвращает имя файла, включая расширение. Например, вызов `GetFileName` создать пользователя сообщение о файле *c:\myhtml\myfile.txt* возвращает имя файла *myfile.txt*.  
  
- `GetFilePath` Возвращает полный путь к файлу. Например, вызов `GetFilePath` создать пользователя сообщение о файле `c:\myhtml\myfile.txt` возвращает путь к файлу `c:\myhtml\myfile.txt`.  
  
- [GetFileTitle](#getfiletitle) возвращает имя файла без расширения файла. Например, вызов `GetFileTitle` создать пользователя сообщение о файле *c:\myhtml\myfile.txt* возвращает заголовок файла *myfile*.  
  
### <a name="example"></a>Пример  
  См. в примере [CFileFind::GetFileName](#getfilename).  
  
##  <a name="getfiletitle"></a>  CFileFind::GetFileTitle  
 Эта функция члена заголовок файла.  
  
```  
virtual CString GetFileTitle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Заголовок файла.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `GetFileTitle`.  
  
 `GetFileTitle` является одним из трех `CFileFind` функции-члены, которые возвращают определенные виды имя файла. Ниже перечислены три и как они изменяются.  
  
- [GetFileName](#getfilename) возвращает имя файла, включая расширение. Например, вызов `GetFileName` создать пользователя сообщение о файле *c:\myhtml\myfile.txt* возвращает имя файла *myfile.txt*.  
  
- [GetFilePath](#getfilepath) возвращает полный путь к файлу. Например, вызов `GetFilePath` создать пользователя сообщение о файле *c:\myhtml\myfile.txt* возвращает путь к файлу *c:\myhtml\myfile.txt*.  
  
- `GetFileTitle` Возвращает имя файла без расширения файла. Например, вызов `GetFileTitle` создать пользователя сообщение о файле *c:\myhtml\myfile.txt* возвращает заголовок файла *myfile*.  
  
### <a name="example"></a>Пример  
  См. в примере [CFileFind::GetFileName](#getfilename).  
  
##  <a name="getfileurl"></a>  CFileFind::GetFileURL  
 Вызовите эту функцию-член для извлечения указанный URL-адрес.  
  
```  
virtual CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Полный URL-адрес.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `GetFileURL`.  
  
 `GetFileURL` похож на функцию-член [GetFilePath](#getfilepath), за исключением того, что она возвращает URL-адрес в форме `file://path`. Например, вызов `GetFileURL` полный URL-адрес для *myfile.txt* возвращает URL-адрес `file://c:\myhtml\myfile.txt`.  
  
### <a name="example"></a>Пример  
  См. в примере [CFileFind::GetFileName](#getfilename).  
  
##  <a name="getlastaccesstime"></a>  CFileFind::GetLastAccessTime  
 Вызывайте эту функцию члена, чтобы получить время последнего обращения к указанному файлу.  
  
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
 Ненулевое значение, если выполнение прошло успешно; 0, если операция завершилась неудачей. `GetLastAccessTime` Возвращает 0 только в том случае, если [FindNextFile](#findnextfile) никогда не был вызван на это `CFileFind` объекта.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `GetLastAccessTime`.  
  
> [!NOTE]
>  Не все файловые системы используйте ту же семантику, чтобы реализовать отметку времени, возвращаемое этой функцией. Эта функция может возвращать же значение, возвращенное другие функции отметку времени, если базовой файловой системы или сервер не поддерживает сохранение атрибут времени. См. в разделе [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структура сведения о форматах времени. В некоторых операционных системах возвращаемое значение времени — времени, были зоны локальной машине, что он находится. См. в разделе Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API Дополнительные сведения.  
  
### <a name="example"></a>Пример  
  См. в примере [CFileFind::GetLength](#getlength).  
  
##  <a name="getlastwritetime"></a>  CFileFind::GetLastWriteTime  
 Вызывайте эту функцию члена, чтобы получить время последнего изменения файла.  
  
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
 Ненулевое значение, если выполнение прошло успешно; 0, если операция завершилась неудачей. `GetLastWriteTime` Возвращает 0 только в том случае, если [FindNextFile](#findnextfile) никогда не был вызван на это `CFileFind` объекта.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `GetLastWriteTime`.  
  
> [!NOTE]
>  Не все файловые системы используйте ту же семантику, чтобы реализовать отметку времени, возвращаемое этой функцией. Эта функция может возвращать же значение, возвращенное другие функции отметку времени, если базовой файловой системы или сервер не поддерживает сохранение атрибут времени. См. в разделе [Win32_Find_Data](http://msdn.microsoft.com/library/windows/desktop/aa365740) структура сведения о форматах времени. В некоторых операционных системах возвращаемое значение времени — времени, были зоны локальной машине, что он находится. См. в разделе Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API Дополнительные сведения.  
  
### <a name="example"></a>Пример  
  См. в примере [CFileFind::GetLength](#getlength).  
  
##  <a name="getlength"></a>  CFileFind::GetLength  
 Вызов этой функции-члена для получения длины файла, в байтах.  
  
```  
ULONGLONG GetLength() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина найденного файла, в байтах.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `GetLength`.  
  
 `GetLength` используется структура Win32 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) для получения и возврата значения размер файла в байтах.  
  
> [!NOTE]
>  Начиная с MFC 7.0 `GetLength` поддерживает 64-разрядными целочисленными типами. Ранее существующий код, созданный с помощью этой новой версии библиотеки может привести предупреждения об усечении.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#33](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_3.cpp)]  
  
##  <a name="getroot"></a>  CFileFind::GetRoot  
 Вызов этой функции-члена для получения корневого файла.  
  
```  
virtual CString GetRoot() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Корень активного поиска.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `GetRoot`.  
  
 Эта функция-член возвращает описатель диска и путь, используемый для запуска поиска. Например, вызов [FindFile](#findfile) с `*.dat` приводит `GetRoot` возвращает пустую строку. При передаче пути, такие как `c:\windows\system\*.dll`, `FindFile` результатов `GetRoot` возврат `c:\windows\system\`.  
  
### <a name="example"></a>Пример  
  См. в примере [CFileFind::GetFileName](#getfilename).  
  
##  <a name="isarchived"></a>  CFileFind::IsArchived  
 Вызывайте эту функцию член, чтобы определить, если выполняется архивирование найденного файла.  
  
```  
BOOL IsArchived() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Приложения пометить файл архива, который является для резервного копирования или удаления, с FILE_ATTRIBUTE_ARCHIVE, атрибут файла, указанного в [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры.  
  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `IsArchived`.  
  
 Функция-член см. в разделе [MatchesMask](#matchesmask) полный список атрибутов файлов.  
  
### <a name="example"></a>Пример  
  См. в примере [CFileFind::GetLength](#getlength).  
  
##  <a name="iscompressed"></a>  CFileFind::IsCompressed  
 Вызывайте эту функцию члена, чтобы определить, если найден файл сжимается.  
  
```  
BOOL IsCompressed() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Сжатый файл помечается FILE_ATTRIBUTE_COMPRESSED, идентифицирован файлового атрибута [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры. Для файла этот атрибут указывает, что все данные в файле сжата. Для каталога этот атрибут указывает, что сжатие используется по умолчанию для вновь создаваемых файлов и подкаталогов.  
  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `IsCompressed`.  
  
 Функция-член см. в разделе [MatchesMask](#matchesmask) полный список атрибутов файлов.  
  
### <a name="example"></a>Пример  
  См. в примере [CFileFind::GetLength](#getlength).  
  
##  <a name="isdirectory"></a>  CFileFind::IsDirectory  
 Вызывайте эту функцию члена, чтобы определить, если найден файл является каталогом.  
  
```  
BOOL IsDirectory() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Файл, который является каталогом помечается FILE_ATTRIBUTE_DIRECTORY атрибут файла, заданный в [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры.  
  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `IsDirectory`.  
  
 Функция-член см. в разделе [MatchesMask](#matchesmask) полный список атрибутов файлов.  
  
### <a name="example"></a>Пример  
 Это небольшая программа рекурсивно проходит каждый каталог на диске C:\ и выводит имя каталога.  
  
 [!code-cpp[NVC_MFCFiles#34](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_4.cpp)]  
  
##  <a name="isdots"></a>  CFileFind::IsDots  
 Вызовите эта функция-член для проверки текущего каталога и родительского маркеры каталог при переборе файлы.  
  
```  
virtual BOOL IsDots() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если найден файл имеет имя «. «или»..», который указывает, что найденный файл является папкой. В противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `IsDots`.  
  
### <a name="example"></a>Пример  
  См. в примере [CFileFind::IsDirectory](#isdirectory).  
  
##  <a name="ishidden"></a>  CFileFind::IsHidden  
 Вызывайте эту функцию члена, чтобы определить, является ли скрытым найденного файла.  
  
```  
BOOL IsHidden() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Скрытые файлы, которые помечены с FILE_ATTRIBUTE_HIDDEN, атрибут файла, заданный в [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры. Скрытый файл не включается в обычный список каталога.  
  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `IsHidden`.  
  
 Функция-член см. в разделе [MatchesMask](#matchesmask) полный список атрибутов файлов.  
  
### <a name="example"></a>Пример  
  См. в примере [CFileFind::GetLength](#getlength).  
  
##  <a name="isnormal"></a>  CFileFind::IsNormal  
 Вызывайте эту функцию члена, чтобы определить, если найден файл является обычным.  
  
```  
BOOL IsNormal() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Файлы с FILE_ATTRIBUTE_NORMAL, атрибут файла, заданный в [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры. Обычный файл имеет другие атрибуты не установлены. Все другие атрибуты файла переопределить этот атрибут.  
  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `IsNormal`.  
  
 Функция-член см. в разделе [MatchesMask](#matchesmask) полный список атрибутов файлов.  
  
### <a name="example"></a>Пример  
  См. в примере [CFileFind::GetLength](#getlength).  
  
##  <a name="isreadonly"></a>  CFileFind::IsReadOnly  
 Вызывайте эту функцию члена, чтобы определить, если найден файл доступен только для чтения.  
  
```  
BOOL IsReadOnly() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Файл, доступный только для чтения помечается FILE_ATTRIBUTE_READONLY, идентифицирован файлового атрибута [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры. Приложения могут читать такой файл, но не могут записывать данные в него и удалите его.  
  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `IsReadOnly`.  
  
 Функция-член см. в разделе [MatchesMask](#matchesmask) полный список атрибутов файлов.  
  
### <a name="example"></a>Пример  
  См. в примере [CFileFind::GetLength](#getlength).  
  
##  <a name="issystem"></a>  CFileFind::IsSystem  
 Вызывайте эту функцию члена, чтобы определить, если найден файл является системным файлом.  
  
```  
BOOL IsSystem() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Системный файл помечается FILE_ATTRIBUTE_SYSTEM, атрибут файла, заданный в [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры. Системный файл является частью, или используется исключительно, операционной системой.  
  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `IsSystem`.  
  
 Функция-член см. в разделе [MatchesMask](#matchesmask) полный список атрибутов файлов.  
  
### <a name="example"></a>Пример  
  См. в примере [CFileFind::GetLength](#getlength).  
  
##  <a name="istemporary"></a>  CFileFind::IsTemporary  
 Вызов этой функции-члена для определения того, является ли найденного файла во временный файл.  
  
```  
BOOL IsTemporary() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Временный файл помечается FILE_ATTRIBUTE_TEMPORARY, идентифицирован файлового атрибута [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры. Временный файл используется для временного хранения. Приложения следует записать в файл только в том случае, если это абсолютно необходимо. Большая часть файла данных остается в памяти без, записываемых на носитель, так как файл скоро будет удален.  
  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `IsTemporary`.  
  
 Функция-член см. в разделе [MatchesMask](#matchesmask) полный список атрибутов файлов.  
  
### <a name="example"></a>Пример  
  См. в примере [CFileFind::GetLength](#getlength).  
  
##  <a name="m_ptm"></a>  CFileFind::m_pTM  
 Указатель на `CAtlTransactionManager` объект.  
  
```  
CAtlTransactionManager* m_pTM;  
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="matchesmask"></a>  CFileFind::MatchesMask  
 Эта функция члена для тестирования атрибуты найденного файла.  
  
```  
virtual BOOL MatchesMask(DWORD dwMask) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *dwMask*  
 Указывает один или несколько атрибутов файла, указанного в [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуру для найденного файла. Для поиска нескольких атрибутов, используйте операцию побитового или (&#124;) оператор. Допустимо любое сочетание следующих атрибутов:  
  
-   FILE_ATTRIBUTE_ARCHIVE файл представляет собой файл архива. Приложения используют этот атрибут для пометки файлов для резервного копирования или удаления.  
  
-   Сжимается FILE_ATTRIBUTE_COMPRESSED файлу или каталогу. Для файла это означает, что все данные в файле сжата. Для каталога это означает, что сжатие используется по умолчанию для вновь создаваемых файлов и подкаталогов.  
  
-   FILE_ATTRIBUTE_DIRECTORY файл является каталогом.  
  
-   FILE_ATTRIBUTE_NORMAL файл имеет другие атрибуты не установлены. Этот атрибут действителен только в том случае, если используется отдельно. Все другие атрибуты файла переопределить этот атрибут.  
  
-   FILE_ATTRIBUTE_HIDDEN файл является скрытым. Это не должны быть включены в обычный список каталога.  
  
-   FILE_ATTRIBUTE_READONLY файл доступен только для чтения. Приложения можно прочитать файл, но нельзя записывать данные в него или удалите его.  
  
-   FILE_ATTRIBUTE_SYSTEM файл является частью, или используется исключительно операционной системой.  
  
-   FILE_ATTRIBUTE_TEMPORARY файл используется для временного хранения. Приложения следует записать в файл только в том случае, если это абсолютно необходимо. Большая часть файла данных остается в памяти без, записываемых на носитель, так как файл скоро будет удален.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Чтобы получить расширенные сведения об ошибке, вызовите функцию Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `MatchesMask`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#35](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_5.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Класс CObject](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)   
 [Класс CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)   
 [Класс CInternetFile](../../mfc/reference/cinternetfile-class.md)   
 [Класс CGopherFile](../../mfc/reference/cgopherfile-class.md)   
 [Класс CHttpFile](../../mfc/reference/chttpfile-class.md)
