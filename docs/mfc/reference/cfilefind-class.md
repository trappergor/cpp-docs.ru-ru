---
title: Класс CFileFind | Документы Microsoft
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
ms.openlocfilehash: cf77a5581dd9e8c9181c61287b6032f700d7d64b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376575"
---
# <a name="cfilefind-class"></a>Класс CFileFind
Выполняет поиск локального файла и является базовым классом для [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) и [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md), которые выполняют поиск файлов Интернета.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CFileFind : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFileFind::CFileFind](#cfilefind)|Создает объект `CFileFind`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFileFind::Close](#close)|Закрывает этот запрос поиска.|  
|[CFileFind::FindFile](#findfile)|Осуществляет поиск указанного имени файла в каталоге.|  
|[CFileFind::FindNextFile](#findnextfile)|Продолжает поиск файла из предыдущего вызова [FindFile](#findfile).|  
|[CFileFind::GetCreationTime](#getcreationtime)|Возвращает время создания файла.|  
|[CFileFind::GetFileName](#getfilename)|Возвращает имя, включая расширение файла|  
|[CFileFind::GetFilePath](#getfilepath)|Возвращает полный путь файла.|  
|[CFileFind::GetFileTitle](#getfiletitle)|Получает название найденного файла. Заголовок не включает расширение.|  
|[CFileFind::GetFileURL](#getfileurl)|Возвращает URL-адрес, включая путь к файлу, найденного файла.|  
|[CFileFind::GetLastAccessTime](#getlastaccesstime)|Возвращает время последнего доступа к файлу.|  
|[CFileFind::GetLastWriteTime](#getlastwritetime)|Получает время файла последнего был изменен и сохранен.|  
|[CFileFind::GetLength](#getlength)|Получает длину файла, в байтах.|  
|[CFileFind::GetRoot](#getroot)|Возвращает корневой каталог файла.|  
|[CFileFind::IsArchived](#isarchived)|Определяет, архивируется ли найденного файла.|  
|[CFileFind::IsCompressed](#iscompressed)|Определяет, если найден файл сжимается.|  
|[CFileFind::IsDirectory](#isdirectory)|Определяет, является ли найденный файл каталога.|  
|[CFileFind::IsDots](#isdots)|Определяет, имеет ли имя найденного файла имя «. «или»..», означает, что является папкой.|  
|[CFileFind::IsHidden](#ishidden)|Определяет, является ли скрытым найденного файла.|  
|[CFileFind::IsNormal](#isnormal)|Определяет, является ли обычный найденный файл (другими словами, не имеет других атрибутов).|  
|[CFileFind::IsReadOnly](#isreadonly)|Определяет, является ли найденный файл только для чтения.|  
|[CFileFind::IsSystem](#issystem)|Определяет, является ли найденный файл системный файл.|  
|[CFileFind::IsTemporary](#istemporary)|Определяет, является ли временные найденного файла.|  
|[CFileFind::MatchesMask](#matchesmask)|Указывает атрибуты файла, чтобы найти нужный файл.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFileFind::CloseContext](#closecontext)|Закрывает файл, указанный в дескрипторе текущего поиска.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFileFind::m_pTM](#m_ptm)|Указатель на `CAtlTransactionManager` объект.|  
  
## <a name="remarks"></a>Примечания  
 `CFileFind` включает функции-члены, начать поиск, найдите файл и возвращает заголовок, имя или путь к файлу. Для поиска в Интернете, функция-член [GetFileURL](#getfileurl) возвращает URL-адрес файла.  
  
 `CFileFind` базовым классом для двух других классов MFC предназначен для поиска конкретного сервера типов: `CGopherFileFind` предназначен для работы с серверами gopher и `CFtpFileFind` предназначен для работы с FTP-серверах. Вместе эти три класса обеспечивают удобный механизм для клиента, чтобы найти файлы, независимо от того, протокол сервера, тип файла или расположение на локальном компьютере или на удаленном сервере.  
  
 Перечисляет все файлы в текущем каталоге, печать имени каждого файла следующий код:  
  
 [!code-cpp[NVC_MFCFiles#31](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_1.cpp)]  
  
 Для простоты, этот код использует стандартную библиотеку C++ `cout` класса. `cout` Строки, можно заменить на вызов `CListBox::AddString`, например, в приложении с помощью графического интерфейса пользователя.  
  
 Дополнительные сведения об использовании `CFileFind` и WinInet классов см. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CFileFind`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="cfilefind"></a>  CFileFind::CFileFind  
 Эта функция-член вызывается, когда `CFileFind` создается объект.  
  
```  
CFileFind();  
CFileFind(CAtlTransactionManager* pTM);
```  
  
### <a name="parameters"></a>Параметры  
 `pTM`  
 Указатель на объект CAtlTransactionManager.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CFileFind::GetFileName](#getfilename).  
  
##  <a name="close"></a>  CFileFind::Close  
 Вызовите эту функцию-член завершить поиск, сброса контекста и освободить все ресурсы.  
  
```  
void Close();
```  
  
### <a name="remarks"></a>Примечания  
 После вызова метода **закрыть**, необходимо создать новый `CFileFind` экземпляр до вызова метода [FindFile](#findfile) чтобы начать новый поиск.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CFileFind::GetFileName](#getfilename).  
  
##  <a name="closecontext"></a>  CFileFind::CloseContext  
 Закрывает файл, указанный в дескрипторе текущего поиска.  
  
```  
virtual void CloseContext();
```  
  
### <a name="remarks"></a>Примечания  
 Закрывает файл, указанный дескриптор поиска текущее значение. Переопределите эту функцию для изменения поведения по умолчанию.  
  
 Необходимо вызвать [FindFile](#findfile) или [FindNextFile](#findnextfile) функции по крайней мере один раз для получения дескриптора допустимые поиска. **FindFile** и `FindNextFile` функции использовать дескриптор поиска для нахождения файлов с именами, совпадающими с указанным именем.  
  
##  <a name="findfile"></a>  CFileFind::FindFile  
 Вызовите эту функцию-член для открытия поиска файла.  
  
```  
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,  
    DWORD dwUnused = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `pstrName`  
 Указатель на строку, содержащую имя файла для поиска. Если передать **NULL** для `pstrName`, **FindFile** подстановочный знак (*.\*) поиска.  
  
 *dwUnused*  
 Зарезервированные вносить **FindFile** полиморфного с производными классами. Должно быть 0.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Чтобы получить расширенные сведения об ошибке, вызовите функцию Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Примечания  
 После вызова метода **FindFile** чтобы начать поиск, вызовите [FindNextFile](#findnextfile) для получения последующих файлов. Необходимо вызвать метод `FindNextFile` по крайней мере один раз перед вызовом любого из следующих атрибутов функции-члены:  
  
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
  
- [isHidden](#ishidden)  
  
- [IsNormal](#isnormal)  
  
- [IsReadOnly](#isreadonly)  
  
- [IsSystem](#issystem)  
  
- [IsTemporary](#istemporary)  
  
- [MatchesMask](#matchesmask)  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CFileFind::IsDirectory](#isdirectory).  
  
##  <a name="findnextfile"></a>  CFileFind::FindNextFile  
 Вызовите эту функцию-член для продолжения поиска файла из предыдущего вызова [FindFile](#findfile).  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если имеется несколько файлов; нуль, если найден файл является последним элементом в каталоге или произошла ошибка. Чтобы получить расширенные сведения об ошибке, вызовите функцию Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360). Если найден файл последний файл в каталоге, или если соответствующие файлы можно найти, `GetLastError` функция возвращает ERROR_NO_MORE_FILES.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать метод `FindNextFile` по крайней мере один раз перед вызовом любого из следующих атрибутов функции-члены:  
  
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
  
- [isHidden](#ishidden)  
  
- [IsNormal](#isnormal)  
  
- [IsReadOnly](#isreadonly)  
  
- [IsSystem](#issystem)  
  
- [IsTemporary](#istemporary)  
  
- [MatchesMask](#matchesmask)  
  
 `FindNextFile` Создает оболочку для функции Win32 [FindNextFile](http://msdn.microsoft.com/library/windows/desktop/aa364428).  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CFileFind::IsDirectory](#isdirectory).  
  
##  <a name="getcreationtime"></a>  CFileFind::GetCreationTime  
 Вызовите эту функцию-член, чтобы получить время создания указанного файла.  
  
```  
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetCreationTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pTimeStamp`  
 Указатель на [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) структуру, содержащую время создания файла.  
  
 `refTime`  
 Ссылку на [CTime](../../atl-mfc-shared/reference/ctime-class.md) объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно; 0, если операция завершилась неудачей. `GetCreationTime` Возвращает 0 только в том случае, если [FindNextFile](#findnextfile) никогда не был вызван для этого `CFileFind` объекта.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `GetCreationTime`.  
  
> [!NOTE]
>  Не все файловые системы для реализации отметку времени, возвращаемое этой функцией, используйте ту же семантику. Эта функция может возвращать то же значение, возвращенное функцией другие функции отметки времени, если базовой файловой системы или сервер не поддерживает сохранение атрибутов времени. В разделе [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структура сведения о форматах времени. В некоторых операционных системах возвращаемое значение времени — времени, были локальной зоны на компьютере, он находится. В разделе Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API-Интерфейс для получения дополнительной информации.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CFileFind::GetLength](#getlength).  
  
##  <a name="getfilename"></a>  CFileFind::GetFileName  
 Вызовите эту функцию-член для получения имени файла.  
  
```  
virtual CString GetFileName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя файла недавно было обнаружено.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом GetFileName.  
  
 `GetFileName` является одним из трех `CFileFind` функции-члены, возвращают определенные виды имя файла. Ниже описаны три и как они отличаются.  
  
- `GetFileName` Возвращает имя файла, включая расширение. Например, вызов `GetFileName` для создания пользовательского сообщения о файле `c:\myhtml\myfile.txt` возвращает имя файла `myfile.txt`.  
  
- [GetFilePath](#getfilepath) возвращает полный путь к файлу. Например, вызов `GetFilePath` для создания пользовательского сообщения о файле `c:\myhtml\myfile.txt` возвращает путь к файлу `c:\myhtml\myfile.txt`.  
  
- [GetFileTitle](#getfiletitle) возвращает имя файла без расширения файла. Например, вызов `GetFileTitle` для создания пользовательского сообщения о файле `c:\myhtml\myfile.txt` возвращает заголовок файла `myfile`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#32](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_2.cpp)]  
  
##  <a name="getfilepath"></a>  CFileFind::GetFilePath  
 Вызовите эту функцию-член для получения полного пути для заданного файла.  
  
```  
virtual CString GetFilePath() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Путь указанного файла.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `GetFilePath`.  
  
 `GetFilePath` является одним из трех `CFileFind` функции-члены, возвращают определенные виды имя файла. Ниже описаны три и как они отличаются.  
  
- [GetFileName](#getfilename) возвращает имя файла, включая расширение. Например, вызов `GetFileName` для создания пользовательского сообщения о файле `c:\myhtml\myfile.txt` возвращает имя файла `myfile.txt`.  
  
- `GetFilePath` Возвращает полный путь к файлу. Например, вызов `GetFilePath` для создания пользовательского сообщения о файле `c:\myhtml\myfile.txt` возвращает путь к файлу `c:\myhtml\myfile.txt`.  
  
- [GetFileTitle](#getfiletitle) возвращает имя файла без расширения файла. Например, вызов `GetFileTitle` для создания пользовательского сообщения о файле `c:\myhtml\myfile.txt` возвращает заголовок файла `myfile`.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CFileFind::GetFileName](#getfilename).  
  
##  <a name="getfiletitle"></a>  CFileFind::GetFileTitle  
 Вызовите эту функцию-член для получения заголовка файла.  
  
```  
virtual CString GetFileTitle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Заголовок файла.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `GetFileTitle`.  
  
 `GetFileTitle` является одним из трех `CFileFind` функции-члены, возвращают определенные виды имя файла. Ниже описаны три и как они отличаются.  
  
- [GetFileName](#getfilename) возвращает имя файла, включая расширение. Например, вызов `GetFileName` для создания пользовательского сообщения о файле `c:\myhtml\myfile.txt` возвращает имя файла `myfile.txt`.  
  
- [GetFilePath](#getfilepath) возвращает полный путь к файлу. Например, вызов `GetFilePath` для создания пользовательского сообщения о файле `c:\myhtml\myfile.txt` возвращает путь к файлу `c:\myhtml\myfile.txt`.  
  
- `GetFileTitle` Возвращает имя файла без расширения файла. Например, вызов `GetFileTitle` для создания пользовательского сообщения о файле `c:\myhtml\myfile.txt` возвращает заголовок файла `myfile`.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CFileFind::GetFileName](#getfilename).  
  
##  <a name="getfileurl"></a>  CFileFind::GetFileURL  
 Вызовите эту функцию-член для извлечения указанный URL-адрес.  
  
```  
virtual CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Полный URL-адрес.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `GetFileURL`.  
  
 `GetFileURL` похожа на функцию-член [GetFilePath](#getfilepath), за исключением того, что она возвращает URL-адрес в форме `file://path`. Например, вызов `GetFileURL` полный URL-адрес для `myfile.txt` возвращает URL-адрес `file://c:\myhtml\myfile.txt`.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CFileFind::GetFileName](#getfilename).  
  
##  <a name="getlastaccesstime"></a>  CFileFind::GetLastAccessTime  
 Вызовите эту функцию-член для получения времени последнего обращения к указанному файлу.  
  
```  
virtual BOOL GetLastAccessTime(CTime& refTime) const;  
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `refTime`  
 Ссылку на [CTime](../../atl-mfc-shared/reference/ctime-class.md) объекта.  
  
 `pTimeStamp`  
 Указатель на [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) структуру, содержащую время последнего доступа к файлу.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно; 0, если операция завершилась неудачей. `GetLastAccessTime` Возвращает 0 только в том случае, если [FindNextFile](#findnextfile) никогда не был вызван для этого `CFileFind` объекта.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `GetLastAccessTime`.  
  
> [!NOTE]
>  Не все файловые системы для реализации отметку времени, возвращаемое этой функцией, используйте ту же семантику. Эта функция может возвращать то же значение, возвращенное функцией другие функции отметки времени, если базовой файловой системы или сервер не поддерживает сохранение атрибутов времени. В разделе [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структура сведения о форматах времени. В некоторых операционных системах возвращаемое значение времени — времени, были локальной зоны на компьютере, он находится. В разделе Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API-Интерфейс для получения дополнительной информации.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CFileFind::GetLength](#getlength).  
  
##  <a name="getlastwritetime"></a>  CFileFind::GetLastWriteTime  
 Вызовите эту функцию-член для получения за время последнего изменения файла.  
  
```  
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetLastWriteTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pTimeStamp`  
 Указатель на [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) структуру, содержащую время последней операции записи файла.  
  
 `refTime`  
 Ссылку на [CTime](../../atl-mfc-shared/reference/ctime-class.md) объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно; 0, если операция завершилась неудачей. `GetLastWriteTime` Возвращает 0 только в том случае, если [FindNextFile](#findnextfile) никогда не был вызван для этого `CFileFind` объекта.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `GetLastWriteTime`.  
  
> [!NOTE]
>  Не все файловые системы для реализации отметку времени, возвращаемое этой функцией, используйте ту же семантику. Эта функция может возвращать то же значение, возвращенное функцией другие функции отметки времени, если базовой файловой системы или сервер не поддерживает сохранение атрибутов времени. В разделе [Win32_Find_Data](http://msdn.microsoft.com/library/windows/desktop/aa365740) структура сведения о форматах времени. В некоторых операционных системах возвращаемое значение времени — времени, были локальной зоны на компьютере, он находится. В разделе Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API-Интерфейс для получения дополнительной информации.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CFileFind::GetLength](#getlength).  
  
##  <a name="getlength"></a>  CFileFind::GetLength  
 Вызовите эту функцию-член получить длину найденного файла в байтах.  
  
```  
ULONGLONG GetLength() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина найденного файла в байтах.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `GetLength`.  
  
 `GetLength` используется структура Win32 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) для получения и возвращаемое значение размера файла в байтах.  
  
> [!NOTE]
>  Начиная с MFC 7.0 `GetLength` поддерживает 64-разрядного целого типа. Ранее существующего кода, созданного с помощью этой новой версии библиотеки может привести к предупреждениям усечение.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#33](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_3.cpp)]  
  
##  <a name="getroot"></a>  CFileFind::GetRoot  
 Вызовите эту функцию-член для получения корневого файла.  
  
```  
virtual CString GetRoot() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Корень активного поиска.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `GetRoot`.  
  
 Эта функция-член возвращает описатель диска и путь, используемый для начала поиска. Например, вызов [FindFile](#findfile) с `*.dat` приводит к `GetRoot` возвращает пустую строку. Передача пути, такие как `c:\windows\system\*.dll`в **FindFile** результатов `GetRoot` возврат `c:\windows\system\`.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CFileFind::GetFileName](#getfilename).  
  
##  <a name="isarchived"></a>  CFileFind::IsArchived  
 Вызовите эту функцию-член для определения, если архивируется найденного файла.  
  
```  
BOOL IsArchived() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Приложения пометить в файл архива, который должен быть резервного копирования или удалена с FILE_ATTRIBUTE_ARCHIVE атрибут файла, указанного в [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры.  
  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `IsArchived`.  
  
 Функция-член в разделе [MatchesMask](#matchesmask) полный список атрибутов файлов.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CFileFind::GetLength](#getlength).  
  
##  <a name="iscompressed"></a>  CFileFind::IsCompressed  
 Вызовите эту функцию-член для определения, если найден файл сжимается.  
  
```  
BOOL IsCompressed() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Сжатый файл помечается FILE_ATTRIBUTE_COMPRESSED, идентифицирован атрибут файла [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры. В файле этот атрибут указывает, что все данные в файл сжимается. Для каталога этот атрибут указывает, что сжатие используется по умолчанию для вновь создаваемых файлов и подкаталогов.  
  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `IsCompressed`.  
  
 Функция-член в разделе [MatchesMask](#matchesmask) полный список атрибутов файлов.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CFileFind::GetLength](#getlength).  
  
##  <a name="isdirectory"></a>  CFileFind::IsDirectory  
 Вызовите эту функцию-член для определения, если найден файл является каталогом.  
  
```  
BOOL IsDirectory() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Файл, который является каталогом помечается атрибут файла, заданный в FILE_ATTRIBUTE_DIRECTORY [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры.  
  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `IsDirectory`.  
  
 Функция-член в разделе [MatchesMask](#matchesmask) полный список атрибутов файлов.  
  
### <a name="example"></a>Пример  
 Этот небольшой программа рекурсивно проходит в каждом каталоге диска C:\ и выводит имя каталога.  
  
 [!code-cpp[NVC_MFCFiles#34](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_4.cpp)]  
  
##  <a name="isdots"></a>  CFileFind::IsDots  
 Вызовите эту функцию-член для проверки на наличие каталога и родительский каталог текущего маркеры во время итерации по файлам.  
  
```  
virtual BOOL IsDots() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если найден файл имеет имя «. «или»..», указывающая, что найденный файл — это каталог. В противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `IsDots`.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CFileFind::IsDirectory](#isdirectory).  
  
##  <a name="ishidden"></a>  CFileFind::IsHidden  
 Вызовите эту функцию-член для определения, является ли скрытым найденного файла.  
  
```  
BOOL IsHidden() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Скрытые файлы, которые помечены с FILE_ATTRIBUTE_HIDDEN файлового атрибута определены в [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры. Скрытый файл не включен в обычный список каталога.  
  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `IsHidden`.  
  
 Функция-член в разделе [MatchesMask](#matchesmask) полный список атрибутов файлов.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CFileFind::GetLength](#getlength).  
  
##  <a name="isnormal"></a>  CFileFind::IsNormal  
 Вызовите эту функцию-член для определения, если найден файл является обычным.  
  
```  
BOOL IsNormal() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Файлы с FILE_ATTRIBUTE_NORMAL, атрибут файл, заданный в [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры. Обычный файл имеет другие атрибуты не установлены. Все остальные атрибуты файла переопределить этот атрибут.  
  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `IsNormal`.  
  
 Функция-член в разделе [MatchesMask](#matchesmask) полный список атрибутов файлов.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CFileFind::GetLength](#getlength).  
  
##  <a name="isreadonly"></a>  CFileFind::IsReadOnly  
 Вызовите эту функцию-член для определения, если найден файл доступен только для чтения.  
  
```  
BOOL IsReadOnly() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Только для чтения файл помечается FILE_ATTRIBUTE_READONLY, идентифицирован атрибут файла [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры. Приложения могут читать такой файл, но их нельзя записать в него или удалите его.  
  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `IsReadOnly`.  
  
 Функция-член в разделе [MatchesMask](#matchesmask) полный список атрибутов файлов.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CFileFind::GetLength](#getlength).  
  
##  <a name="issystem"></a>  CFileFind::IsSystem  
 Вызовите эту функцию-член для определения, если найден файл является системным.  
  
```  
BOOL IsSystem() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Системный файл помечается FILE_ATTRIBUTE_SYSTEM, атрибут файла, заданный в [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры. Системный файл является частью или используется исключительно в операционной системе.  
  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `IsSystem`.  
  
 Функция-член в разделе [MatchesMask](#matchesmask) полный список атрибутов файлов.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CFileFind::GetLength](#getlength).  
  
##  <a name="istemporary"></a>  CFileFind::IsTemporary  
 Вызовите эту функцию-член для определения, если найден файл во временный файл.  
  
```  
BOOL IsTemporary() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Временный файл помечается FILE_ATTRIBUTE_TEMPORARY, идентифицирован атрибут файла [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры. Временный файл используется для временного хранения. Запись в файл приложения следует только в том случае, если это действительно необходимо. Большая часть файла данных остается в памяти без, записываемых на носитель, так как файл будут удалены.  
  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `IsTemporary`.  
  
 Функция-член в разделе [MatchesMask](#matchesmask) полный список атрибутов файлов.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CFileFind::GetLength](#getlength).  
  
##  <a name="m_ptm"></a>  CFileFind::m_pTM  
 Указатель на `CAtlTransactionManager` объект.  
  
```  
CAtlTransactionManager* m_pTM;  
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="matchesmask"></a>  CFileFind::MatchesMask  
 Вызовите эту функцию-член для проверки атрибутов файла на найденный файл.  
  
```  
virtual BOOL MatchesMask(DWORD dwMask) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `dwMask`  
 Указывает один или несколько атрибутов файлов, указанных в [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуру для найденного файла. Для поиска нескольких атрибутов, используйте побитовый оператор или (&#124;) оператор. Допускается любое сочетание следующих атрибутов:  
  
-   FILE_ATTRIBUTE_ARCHIVE файл представляет собой файл архива. Приложения используют этот атрибут, чтобы пометить файлы для резервного копирования или удаления.  
  
-   Сжимается FILE_ATTRIBUTE_COMPRESSED к файлу или каталогу. Для файла это означает, что все данные в файл сжимается. Для каталога, а это означает, что сжатие используется по умолчанию для вновь создаваемых файлов и подкаталогов.  
  
-   FILE_ATTRIBUTE_DIRECTORY файл является каталогом.  
  
-   FILE_ATTRIBUTE_NORMAL файл имеет другие атрибуты не установлены. Этот атрибут действителен только в том случае, если используется отдельно. Все остальные атрибуты файла переопределить этот атрибут.  
  
-   FILE_ATTRIBUTE_HIDDEN файл будет скрыта. Это не должно включаться в обычный список каталога.  
  
-   FILE_ATTRIBUTE_READONLY файл доступен только для чтения. Приложения можно прочитать файл, но нельзя записать в него или удалите его.  
  
-   FILE_ATTRIBUTE_SYSTEM файл является частью или используется исключительно операционной системой.  
  
-   FILE_ATTRIBUTE_TEMPORARY файл используется для временного хранения. Запись в файл приложения следует только в том случае, если это действительно необходимо. Большая часть файла данных остается в памяти без, записываемых на носитель, так как файл будут удалены.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Чтобы получить расширенные сведения об ошибке, вызовите функцию Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом `MatchesMask`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#35](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_5.cpp)]  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)   
 [Класс CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)   
 [Класс классе CInternetFile](../../mfc/reference/cinternetfile-class.md)   
 [Класс CGopherFile](../../mfc/reference/cgopherfile-class.md)   
 [Класс CHttpFile](../../mfc/reference/chttpfile-class.md)
