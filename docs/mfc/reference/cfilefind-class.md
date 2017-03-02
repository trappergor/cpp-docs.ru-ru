---
title: "Класс CFileFind | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFileFind
dev_langs:
- C++
helpviewer_keywords:
- files [C++], finding
- Internet files [C++], finding
- CFileFind class
- URLs [C++], searching for
- local files
- local files, searching for
ms.assetid: 9990068c-b023-4114-9580-a50182d15240
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
ms.openlocfilehash: d7e6500dfc0ff24f35dd021a54080eb7ba7f1655
ms.lasthandoff: 02/24/2017

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
|[CFileFind::Close](#close)|Закрывает запрос поиска.|  
|[CFileFind::FindFile](#findfile)|Осуществляет поиск указанного имени файла в каталоге.|  
|[CFileFind::FindNextFile](#findnextfile)|Продолжает поиск файла из предыдущего вызова [FindFile](#findfile).|  
|[CFileFind::GetCreationTime](#getcreationtime)|Получает время создания файла.|  
|[CFileFind::GetFileName](#getfilename)|Возвращает имя, включая расширение файла|  
|[CFileFind::GetFilePath](#getfilepath)|Возвращает полный путь файла.|  
|[CFileFind::GetFileTitle](#getfiletitle)|Возвращает заголовок файла. Заголовок не включает расширение.|  
|[CFileFind::GetFileURL](#getfileurl)|Возвращает URL-адрес, включая путь к файлу, найденного файла.|  
|[CFileFind::GetLastAccessTime](#getlastaccesstime)|Получает время последнего доступа к файлу.|  
|[CFileFind::GetLastWriteTime](#getlastwritetime)|Получает время файла последней был изменен и сохранен.|  
|[CFileFind::GetLength](#getlength)|Получает длину файла, в байтах.|  
|[CFileFind::GetRoot](#getroot)|Возвращает корневой каталог файла.|  
|[CFileFind::IsArchived](#isarchived)|Определяет, если найден файл архивируется.|  
|[CFileFind::IsCompressed](#iscompressed)|Определяет, если найден файл сжат.|  
|[CFileFind::IsDirectory](#isdirectory)|Определяет, является ли найденный файл каталога.|  
|[CFileFind::IsDots](#isdots)|Определяет, имеет ли имя найденного файла имя «. «или»..», означает, что является папкой.|  
|[CFileFind::IsHidden](#ishidden)|Определяет, является ли скрытым найденный файл.|  
|[CFileFind::IsNormal](#isnormal)|Определяет, является ли найденный файл normal (другими словами, не имеет других атрибутов).|  
|[CFileFind::IsReadOnly](#isreadonly)|Определяет, является ли найденный файл только для чтения.|  
|[CFileFind::IsSystem](#issystem)|Определяет, является ли найденный файл файловой системы.|  
|[CFileFind::IsTemporary](#istemporary)|Определяет, если найден файл является временным.|  
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
 `CFileFind`включает функции-члены, начать поиск, найдите файл и возвращающие title, имя или путь к файлу. Для поиска в Интернете, эта функция-член [GetFileURL](#getfileurl) возвращает URL-адрес файла.  
  
 `CFileFind`базовым классом для двух других классов MFC предназначен для поиска конкретного сервера типов: `CGopherFileFind` предназначен для работы с серверами gopher и `CFtpFileFind` предназначен для работы с FTP-серверов. Вместе эти три класса механизма эффективной для клиента, чтобы найти файлы, независимо от протокола сервера, тип файла или расположение на локальном компьютере или на удаленном сервере.  
  
 Перечисляет все файлы в текущем каталоге, вывод имени каждого файла следующий код:  
  
 [!code-cpp[NVC_MFCFiles&#31;](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_1.cpp)]  
  
 Для простоты в примере в этом коде используется стандартная библиотека C++ `cout` класса. `cout` Строки может быть заменено вызов `CListBox::AddString`, например, в приложении с помощью графического интерфейса.  
  
 Дополнительные сведения об использовании `CFileFind` и WinInet классов см. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CFileFind`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="a-namecfilefinda--cfilefindcfilefind"></a><a name="cfilefind"></a>CFileFind::CFileFind  
 Эта функция-член вызывается `CFileFind` создается объект.  
  
```  
CFileFind();  
CFileFind(CAtlTransactionManager* pTM);
```  
  
### <a name="parameters"></a>Параметры  
 `pTM`  
 Указатель на объект CAtlTransactionManager.  
  
### <a name="example"></a>Пример  
  В примере показано [CFileFind::GetFileName](#getfilename).  
  
##  <a name="a-nameclosea--cfilefindclose"></a><a name="close"></a>CFileFind::Close  
 Вызовите эту функцию-член завершить поиск, сброса контекста и освободить все ресурсы.  
  
```  
void Close();
```  
  
### <a name="remarks"></a>Примечания  
 После вызова метода **закрыть**, необходимо создать новый `CFileFind` экземпляра перед вызовом метода [FindFile](#findfile) начать новый поиск.  
  
### <a name="example"></a>Пример  
  В примере показано [CFileFind::GetFileName](#getfilename).  
  
##  <a name="a-nameclosecontexta--cfilefindclosecontext"></a><a name="closecontext"></a>CFileFind::CloseContext  
 Закрывает файл, указанный в дескрипторе текущего поиска.  
  
```  
virtual void CloseContext();
```  
  
### <a name="remarks"></a>Примечания  
 Закрывает файл, указанный параметром текущее значение дескриптора поиска. Переопределите эту функцию для изменения поведения по умолчанию.  
  
 Необходимо вызвать [FindFile](#findfile) или [FindNextFile](#findnextfile) функции по крайней мере один раз для получения дескриптора допустимым поиска. **FindFile** и `FindNextFile` функции использовать дескриптор поиска для нахождения файлов с именами, совпадающими с определенным именем.  
  
##  <a name="a-namefindfilea--cfilefindfindfile"></a><a name="findfile"></a>CFileFind::FindFile  
 Вызовите эту функцию-член для открытия поиска файлов.  
  
```  
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,  
    DWORD dwUnused = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `pstrName`  
 Указатель на строку, содержащую имя файла для поиска. Если передать **NULL** для `pstrName`, **FindFile** подстановочный знак (*.\*) поиска.  
  
 *dwUnused*  
 Зарезервированные вносить **FindFile** полиморфных с производными классами. Должно быть 0.  
  
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
  
- [IsHidden](#ishidden)  
  
- [IsNormal](#isnormal)  
  
- [IsReadOnly](#isreadonly)  
  
- [IsSystem](#issystem)  
  
- [IsTemporary](#istemporary)  
  
- [MatchesMask](#matchesmask)  
  
### <a name="example"></a>Пример  
  В примере показано [CFileFind::IsDirectory](#isdirectory).  
  
##  <a name="a-namefindnextfilea--cfilefindfindnextfile"></a><a name="findnextfile"></a>CFileFind::FindNextFile  
 Вызов этой функции-члена для продолжения поиска файла из предыдущего вызова [FindFile](#findfile).  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если существует несколько файлов; нуль, если найден файл является последним элементом в каталоге или если произошла ошибка. Чтобы получить расширенные сведения об ошибке, вызовите функцию Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360). Если найден файл последний файл в каталоге или если соответствующие файлы можно найти, `GetLastError` функция возвращает ERROR_NO_MORE_FILES.  
  
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
  
- [IsHidden](#ishidden)  
  
- [IsNormal](#isnormal)  
  
- [IsReadOnly](#isreadonly)  
  
- [IsSystem](#issystem)  
  
- [IsTemporary](#istemporary)  
  
- [MatchesMask](#matchesmask)  
  
 `FindNextFile`Создает оболочку для функции Win32 [FindNextFile](http://msdn.microsoft.com/library/windows/desktop/aa364428).  
  
### <a name="example"></a>Пример  
  В примере показано [CFileFind::IsDirectory](#isdirectory).  
  
##  <a name="a-namegetcreationtimea--cfilefindgetcreationtime"></a><a name="getcreationtime"></a>CFileFind::GetCreationTime  
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
 Ненулевое значение, если выполнено успешно; 0, если операция завершилась неудачей. `GetCreationTime`Возвращает 0, только если [FindNextFile](#findnextfile) никогда не был вызван для этого `CFileFind` объекта.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом метода `GetCreationTime`.  
  
> [!NOTE]
>  Не все файловые системы используют ту же семантику для реализации отметку времени, возвращаемый этой функцией. Эта функция может возвращать то же значение, возвращенное функцией другие функции отметку времени, если базовой файловой системы или сервер не поддерживает сохранение атрибутов времени. В разделе [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры сведения о форматах времени. В некоторых операционных системах возвращаемое значение времени — времени, были зоны локальной машине, что он находится. В разделе Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API для получения дополнительной информации.  
  
### <a name="example"></a>Пример  
  В примере показано [CFileFind::GetLength](#getlength).  
  
##  <a name="a-namegetfilenamea--cfilefindgetfilename"></a><a name="getfilename"></a>CFileFind::GetFileName  
 Вызовите эту функцию-член для получения имени файла.  
  
```  
virtual CString GetFileName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя файла недавно было обнаружено.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом GetFileName.  
  
 `GetFileName`является одним из трех `CFileFind` функций-членов, возвращающих определенные виды имя файла. Ниже перечислены три и как они зависят.  
  
- `GetFileName`Возвращает имя файла, включая расширение. Например, вызов `GetFileName` для пользователя сообщение о файле `c:\myhtml\myfile.txt` возвращает имя файла `myfile.txt`.  
  
- [GetFilePath](#getfilepath) возвращает полный путь к файлу. Например, вызов `GetFilePath` для пользователя сообщение о файле `c:\myhtml\myfile.txt` возвращает путь к файлу `c:\myhtml\myfile.txt`.  
  
- [GetFileTitle](#getfiletitle) возвращает имя файла без расширения файла. Например, вызов `GetFileTitle` для пользователя сообщение о файле `c:\myhtml\myfile.txt` возвращает заголовок файла `myfile`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles&#32;](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_2.cpp)]  
  
##  <a name="a-namegetfilepatha--cfilefindgetfilepath"></a><a name="getfilepath"></a>CFileFind::GetFilePath  
 Вызовите эту функцию-член для получения полного пути, указанного файла.  
  
```  
virtual CString GetFilePath() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Путь указанного файла.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом метода `GetFilePath`.  
  
 `GetFilePath`является одним из трех `CFileFind` функций-членов, возвращающих определенные виды имя файла. Ниже перечислены три и как они зависят.  
  
- [GetFileName](#getfilename) возвращает имя файла, включая расширение. Например, вызов `GetFileName` для пользователя сообщение о файле `c:\myhtml\myfile.txt` возвращает имя файла `myfile.txt`.  
  
- `GetFilePath`Возвращает полный путь к файлу. Например, вызов `GetFilePath` для пользователя сообщение о файле `c:\myhtml\myfile.txt` возвращает путь к файлу `c:\myhtml\myfile.txt`.  
  
- [GetFileTitle](#getfiletitle) возвращает имя файла без расширения файла. Например, вызов `GetFileTitle` для пользователя сообщение о файле `c:\myhtml\myfile.txt` возвращает заголовок файла `myfile`.  
  
### <a name="example"></a>Пример  
  В примере показано [CFileFind::GetFileName](#getfilename).  
  
##  <a name="a-namegetfiletitlea--cfilefindgetfiletitle"></a><a name="getfiletitle"></a>CFileFind::GetFileTitle  
 Вызовите эту функцию-член заголовок файла.  
  
```  
virtual CString GetFileTitle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Заголовок файла.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом метода `GetFileTitle`.  
  
 `GetFileTitle`является одним из трех `CFileFind` функций-членов, возвращающих определенные виды имя файла. Ниже перечислены три и как они зависят.  
  
- [GetFileName](#getfilename) возвращает имя файла, включая расширение. Например, вызов `GetFileName` для пользователя сообщение о файле `c:\myhtml\myfile.txt` возвращает имя файла `myfile.txt`.  
  
- [GetFilePath](#getfilepath) возвращает полный путь к файлу. Например, вызов `GetFilePath` для пользователя сообщение о файле `c:\myhtml\myfile.txt` возвращает путь к файлу `c:\myhtml\myfile.txt`.  
  
- `GetFileTitle`Возвращает имя файла без расширения файла. Например, вызов `GetFileTitle` для пользователя сообщение о файле `c:\myhtml\myfile.txt` возвращает заголовок файла `myfile`.  
  
### <a name="example"></a>Пример  
  В примере показано [CFileFind::GetFileName](#getfilename).  
  
##  <a name="a-namegetfileurla--cfilefindgetfileurl"></a><a name="getfileurl"></a>CFileFind::GetFileURL  
 Вызовите эту функцию-член для получения указанный URL-адрес.  
  
```  
virtual CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Полный URL-адрес.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом метода `GetFileURL`.  
  
 `GetFileURL`аналогична функции-члена [GetFilePath](#getfilepath), за исключением того, что она возвращает URL-адрес в форме `file://path`. Например, вызов `GetFileURL` Чтобы получить полный URL-адрес для `myfile.txt` возвращает URL-адрес `file://c:\myhtml\myfile.txt`.  
  
### <a name="example"></a>Пример  
  В примере показано [CFileFind::GetFileName](#getfilename).  
  
##  <a name="a-namegetlastaccesstimea--cfilefindgetlastaccesstime"></a><a name="getlastaccesstime"></a>CFileFind::GetLastAccessTime  
 Вызовите эту функцию-член, чтобы получить время последнего обращения к указанному файлу.  
  
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
 Ненулевое значение, если выполнено успешно; 0, если операция завершилась неудачей. `GetLastAccessTime`Возвращает 0, только если [FindNextFile](#findnextfile) никогда не был вызван для этого `CFileFind` объекта.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом метода `GetLastAccessTime`.  
  
> [!NOTE]
>  Не все файловые системы используют ту же семантику для реализации отметку времени, возвращаемый этой функцией. Эта функция может возвращать то же значение, возвращенное функцией другие функции отметку времени, если базовой файловой системы или сервер не поддерживает сохранение атрибутов времени. В разделе [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры сведения о форматах времени. В некоторых операционных системах возвращаемое значение времени — времени, были зоны локальной машине, что он находится. В разделе Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API для получения дополнительной информации.  
  
### <a name="example"></a>Пример  
  В примере показано [CFileFind::GetLength](#getlength).  
  
##  <a name="a-namegetlastwritetimea--cfilefindgetlastwritetime"></a><a name="getlastwritetime"></a>CFileFind::GetLastWriteTime  
 Вызовите эту функцию-член для получения времени последнего изменения файла.  
  
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
 Ненулевое значение, если выполнено успешно; 0, если операция завершилась неудачей. `GetLastWriteTime`Возвращает 0, только если [FindNextFile](#findnextfile) никогда не был вызван для этого `CFileFind` объекта.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом метода `GetLastWriteTime`.  
  
> [!NOTE]
>  Не все файловые системы используют ту же семантику для реализации отметку времени, возвращаемый этой функцией. Эта функция может возвращать то же значение, возвращенное функцией другие функции отметку времени, если базовой файловой системы или сервер не поддерживает сохранение атрибутов времени. В разделе [Win32_Find_Data](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры сведения о форматах времени. В некоторых операционных системах возвращаемое значение времени — времени, были зоны локальной машине, что он находится. В разделе Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API для получения дополнительной информации.  
  
### <a name="example"></a>Пример  
  В примере показано [CFileFind::GetLength](#getlength).  
  
##  <a name="a-namegetlengtha--cfilefindgetlength"></a><a name="getlength"></a>CFileFind::GetLength  
 Вызовите эту функцию-член получить длину файла, в байтах.  
  
```  
ULONGLONG GetLength() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина файла, в байтах.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом метода `GetLength`.  
  
 `GetLength`используется структура Win32 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) для получения и возвращения значения размера файла в байтах.  
  
> [!NOTE]
>  Начиная с MFC 7.0 `GetLength` поддерживает 64-разрядного целого типа. Ранее существующего кода, созданного с помощью этой новой версии библиотеки может привести к усечению предупреждения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles&#33;](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_3.cpp)]  
  
##  <a name="a-namegetroota--cfilefindgetroot"></a><a name="getroot"></a>CFileFind::GetRoot  
 Вызовите эту функцию-член для получения корневого файла.  
  
```  
virtual CString GetRoot() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Корень активного поиска.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом метода `GetRoot`.  
  
 Эта функция-член возвращает описатель диска и путь, используемый для начала поиска. Например, вызов [FindFile](#findfile) с `*.dat` приводит к `GetRoot` возвращает пустую строку. Передача пути, такие как `c:\windows\system\*.dll`, **FindFile** результатов `GetRoot` возврат `c:\windows\system\`.  
  
### <a name="example"></a>Пример  
  В примере показано [CFileFind::GetFileName](#getfilename).  
  
##  <a name="a-nameisarchiveda--cfilefindisarchived"></a><a name="isarchived"></a>CFileFind::IsArchived  
 Вызовите эту функцию-член для определения, если найден файл архивируется.  
  
```  
BOOL IsArchived() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Приложения пометить файл архива резервного копирования или удаления, с FILE_ATTRIBUTE_ARCHIVE атрибут файла, указанного в [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры.  
  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом метода `IsArchived`.  
  
 Функция-член в разделе [MatchesMask](#matchesmask) полный список атрибутов файла.  
  
### <a name="example"></a>Пример  
  В примере показано [CFileFind::GetLength](#getlength).  
  
##  <a name="a-nameiscompresseda--cfilefindiscompressed"></a><a name="iscompressed"></a>CFileFind::IsCompressed  
 Вызовите эту функцию-член для определения, если найден файл сжат.  
  
```  
BOOL IsCompressed() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Сжатый файл помечается FILE_ATTRIBUTE_COMPRESSED, идентифицирован атрибут файла [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры. Для файла этот атрибут указывает, что все данные в файле сжимается. Для каталога этот атрибут указывает, что сжатие используется по умолчанию для вновь создаваемых файлов и подкаталогов.  
  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом метода `IsCompressed`.  
  
 Функция-член в разделе [MatchesMask](#matchesmask) полный список атрибутов файла.  
  
### <a name="example"></a>Пример  
  В примере показано [CFileFind::GetLength](#getlength).  
  
##  <a name="a-nameisdirectorya--cfilefindisdirectory"></a><a name="isdirectory"></a>CFileFind::IsDirectory  
 Вызовите эту функцию-член для определения, если найден файл является каталогом.  
  
```  
BOOL IsDirectory() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Файл, который представляет собой каталог помечается файла атрибут, заданный в FILE_ATTRIBUTE_DIRECTORY [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры.  
  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом метода `IsDirectory`.  
  
 Функция-член в разделе [MatchesMask](#matchesmask) полный список атрибутов файла.  
  
### <a name="example"></a>Пример  
 Это небольшая программа также выполняет рекурсивный просмотр в каждом каталоге диска C:\ и выводит имя каталога.  
  
 [!code-cpp[NVC_MFCFiles&#34;](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_4.cpp)]  
  
##  <a name="a-nameisdotsa--cfilefindisdots"></a><a name="isdots"></a>CFileFind::IsDots  
 Вызовите эту функцию-член для проверки во время итерации файлы каталога и родительский каталог текущего маркеры.  
  
```  
virtual BOOL IsDots() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если найден файл имеет имя «. «или»..», указывает, что найденный файл — это каталог. В противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом метода `IsDots`.  
  
### <a name="example"></a>Пример  
  В примере показано [CFileFind::IsDirectory](#isdirectory).  
  
##  <a name="a-nameishiddena--cfilefindishidden"></a><a name="ishidden"></a>CFileFind::IsHidden  
 Вызовите эту функцию-член, чтобы определить, если найден файл является скрытым.  
  
```  
BOOL IsHidden() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Скрытые файлы, которые помечены с помощью FILE_ATTRIBUTE_HIDDEN, атрибут файла определены в [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры. Скрытый файл не включается в обычный список каталога.  
  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом метода `IsHidden`.  
  
 Функция-член в разделе [MatchesMask](#matchesmask) полный список атрибутов файла.  
  
### <a name="example"></a>Пример  
  В примере показано [CFileFind::GetLength](#getlength).  
  
##  <a name="a-nameisnormala--cfilefindisnormal"></a><a name="isnormal"></a>CFileFind::IsNormal  
 Вызовите эту функцию-член для определения, если найден файл является обычным.  
  
```  
BOOL IsNormal() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Файлы с FILE_ATTRIBUTE_NORMAL, атрибут файл, заданный в [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры. Обычный файл не имеет других атрибутов значение. Все остальные атрибуты файла переопределения этого атрибута.  
  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом метода `IsNormal`.  
  
 Функция-член в разделе [MatchesMask](#matchesmask) полный список атрибутов файла.  
  
### <a name="example"></a>Пример  
  В примере показано [CFileFind::GetLength](#getlength).  
  
##  <a name="a-nameisreadonlya--cfilefindisreadonly"></a><a name="isreadonly"></a>CFileFind::IsReadOnly  
 Вызовите эту функцию-член для определения, если найден файл доступен только для чтения.  
  
```  
BOOL IsReadOnly() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Только для чтения файл помечается FILE_ATTRIBUTE_READONLY, идентифицирован атрибут файла [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры. Приложения могут читать такой файл, но их нельзя записать в него или удалить его.  
  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом метода `IsReadOnly`.  
  
 Функция-член в разделе [MatchesMask](#matchesmask) полный список атрибутов файла.  
  
### <a name="example"></a>Пример  
  В примере показано [CFileFind::GetLength](#getlength).  
  
##  <a name="a-nameissystema--cfilefindissystem"></a><a name="issystem"></a>CFileFind::IsSystem  
 Вызовите эту функцию-член для определения, если найден файл является системным файлом.  
  
```  
BOOL IsSystem() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Системный файл помечается FILE_ATTRIBUTE_SYSTEM, идентифицирован атрибут файла [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры. Системный файл является частью или использоваться исключительно для операционной системы.  
  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом метода `IsSystem`.  
  
 Функция-член в разделе [MatchesMask](#matchesmask) полный список атрибутов файла.  
  
### <a name="example"></a>Пример  
  В примере показано [CFileFind::GetLength](#getlength).  
  
##  <a name="a-nameistemporarya--cfilefindistemporary"></a><a name="istemporary"></a>CFileFind::IsTemporary  
 Вызовите эту функцию-член для определения, если найден файл во временный файл.  
  
```  
BOOL IsTemporary() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Временный файл помечается FILE_ATTRIBUTE_TEMPORARY, идентифицирован атрибут файла [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуры. Временный файл используется для временного хранения. Запись в файл приложения следует только в случае крайней необходимости. Большая часть данных файла остается в памяти без записи на диск на носитель, так как файл будут удалены.  
  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом метода `IsTemporary`.  
  
 Функция-член в разделе [MatchesMask](#matchesmask) полный список атрибутов файла.  
  
### <a name="example"></a>Пример  
  В примере показано [CFileFind::GetLength](#getlength).  
  
##  <a name="a-namemptma--cfilefindmptm"></a><a name="m_ptm"></a>CFileFind::m_pTM  
 Указатель на `CAtlTransactionManager` объект.  
  
```  
CAtlTransactionManager* m_pTM;  
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namematchesmaska--cfilefindmatchesmask"></a><a name="matchesmask"></a>CFileFind::MatchesMask  
 Вызовите эту функцию-член для тестирования на найденный файл атрибутов файла.  
  
```  
virtual BOOL MatchesMask(DWORD dwMask) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `dwMask`  
 Указывает один или несколько атрибутов файлов, указанных в [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структуру для найденный файл. Для поиска нескольких атрибутов, используйте побитовый оператор или оператор (|). Допустимо любое сочетание следующих атрибутов:  
  
-   Файл FILE_ATTRIBUTE_ARCHIVE представляет собой файл архива. Приложения используют этот атрибут, чтобы пометить файлы для резервного копирования или удаления.  
  
-   FILE_ATTRIBUTE_COMPRESSED файл или каталог, сжимаются. Для файла это означает, что все данные в файле сжимается. Для каталога, а это означает, что сжатие используется по умолчанию для вновь создаваемых файлов и подкаталогов.  
  
-   FILE_ATTRIBUTE_DIRECTORY файл представляет собой каталог.  
  
-   FILE_ATTRIBUTE_NORMAL файл не имеет других атрибутов значение. Этот атрибут действителен только в том случае, если используется отдельно. Все остальные атрибуты файла переопределения этого атрибута.  
  
-   FILE_ATTRIBUTE_HIDDEN файл является скрытым. Это не должны быть включены в обычный список каталога.  
  
-   FILE_ATTRIBUTE_READONLY файл доступен только для чтения. Приложения можно прочитать файл, но не может записать в него или удалить.  
  
-   FILE_ATTRIBUTE_SYSTEM является частью файла или используется исключительно операционной системой.  
  
-   FILE_ATTRIBUTE_TEMPORARY файл используется для временного хранения. Запись в файл приложения следует только в случае крайней необходимости. Большая часть данных файла остается в памяти без записи на диск на носитель, так как файл будут удалены.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Чтобы получить расширенные сведения об ошибке, вызовите функцию Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Примечания  
 Необходимо вызвать [FindNextFile](#findnextfile) по крайней мере один раз перед вызовом метода `MatchesMask`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles&#35;](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_5.cpp)]  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)   
 [Класс CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)   
 [Класс CInternetFile](../../mfc/reference/cinternetfile-class.md)   
 [Класс CGopherFile](../../mfc/reference/cgopherfile-class.md)   
 [Класс CHttpFile](../../mfc/reference/chttpfile-class.md)

