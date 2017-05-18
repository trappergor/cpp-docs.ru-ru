---
title: "Класс CFtpFileFind | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFtpFileFind
- AFXINET/CFtpFileFind
- AFXINET/CFtpFileFind::CFtpFileFind
- AFXINET/CFtpFileFind::FindFile
- AFXINET/CFtpFileFind::FindNextFile
- AFXINET/CFtpFileFind::GetFileURL
dev_langs:
- C++
helpviewer_keywords:
- CFtpFileFind class
- file searches [C++]
ms.assetid: 9667cf01-657f-4b11-b9db-f11e5a7b4e4c
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6e84282cc2f22e813ea44318d497c7e32e3280d8
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cftpfilefind-class"></a>Класс CFtpFileFind
Помогает в поиске файлов Интернета на FTP-серверах.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CFtpFileFind : public CFileFind  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFtpFileFind::CFtpFileFind](#cftpfilefind)|Создает объект `CFtpFileFind`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFtpFileFind::FindFile](#findfile)|Поиск файла на FTP-сервере.|  
|[CFtpFileFind::FindNextFile](#findnextfile)|Продолжает поиск файла из предыдущего вызова [FindFile](#findfile).|  
|[CFtpFileFind::GetFileURL](#getfileurl)|Возвращает URL-адрес, включая путь файла.|  
  
## <a name="remarks"></a>Примечания  
 `CFtpFileFind`включает функции-члены, начать поиск, найдите файл и возвращает URL-адрес или другие описательные сведения о файле.  
  
 Другие классы MFC, предназначены для Интернета и поиск локального файла содержат [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) и [CFileFind](../../mfc/reference/cfilefind-class.md). Вместе с `CFtpFileFind`, эти классы предоставляют простой механизм для клиента, чтобы найти определенные файлы, независимо от сервера протокола или тип файла (локальном компьютере или удаленном сервере). Обратите внимание, что класс не MFC для поиска по HTTP-серверы HTTP поддерживает прямое файлами, необходимые для поиска.  
  
 Дополнительные сведения об использовании `CFtpFileFind` и WinInet классов см. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="example"></a>Пример  
 Следующий код демонстрирует для перечисления всех файлов в текущем каталоге FTP-сервера.  
  
 [!code-cpp[NVC_MFCWinInet №&8;](../../mfc/codesnippet/cpp/cftpfilefind-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFileFind](../../mfc/reference/cfilefind-class.md)  
  
 `CFtpFileFind`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxinet.h  
  
##  <a name="cftpfilefind"></a>CFtpFileFind::CFtpFileFind  
 Эта функция-член вызывается для создания `CFtpFileFind` объекта.  
  
```  
explicit CFtpFileFind(
    CFtpConnection* pConnection,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Параметры  
 `pConnection`  
 Указатель на объект `CFtpConnection`. FTP-соединение можно получить, вызвав [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection).  
  
 `dwContext`  
 Идентификатор контекста для `CFtpFileFind` объекта. В разделе **примечания** Дополнительные сведения об этом параметре.  
  
### <a name="remarks"></a>Примечания  
 Значение по умолчанию для `dwContext` отправленных MFC для `CFtpFileFind` объекта из [CInternetSession](../../mfc/reference/cinternetsession-class.md) создания объекта `CFtpFileFind` объекта. Можно переопределить значение по умолчанию для идентификатора контекста параметру значение по своему выбору. Идентификатор контекста возвращается [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) для предоставления состояния объекта, с помощью которого определяется. См. в статье [Интернет первые шаги: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.  
  
### <a name="example"></a>Пример  
  Дополнительные сведения о ранее в этом разделе см.  
  
##  <a name="findfile"></a>CFtpFileFind::FindFile  
 Вызовите эту функцию-член для поиска файла FTP.  
  
```  
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,  
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```  
  
### <a name="parameters"></a>Параметры  
 `pstrName`  
 Указатель на строку, содержащую имя файла для поиска. Если **NULL**, вызов будет выполнять поиск подстановочный знак (*).  
  
 `dwFlags`  
 Флаги, описывающие способ обработки данного сеанса. Эти флаги можно объединить с помощью оператора побитового или (|) и выглядят следующим образом:  
  
-   INTERNET_FLAG_RELOAD получение данных из сети, даже если он кэшируется локально. Это флаг по умолчанию.  
  
-   INTERNET_FLAG_DONT_CACHE не кэшировать данные локально или на всех шлюзов.  
  
-   INTERNET_FLAG_RAW_DATA переопределить значение по умолчанию для возвращения необработанных данных ( [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) структур для FTP).  
  
-   Защищает INTERNET_FLAG_SECURE транзакции по сети с помощью протокола SSL или использованию PCT. Этот флаг применяется только HTTP-запросы.  
  
-   INTERNET_FLAG_EXISTING_CONNECT, если возможно, повторно использовать существующие подключения к серверу для новых **FindFile** запросов вместо создания нового сеанса для каждого запроса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Чтобы получить расширенные сведения об ошибке, вызовите функцию Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Примечания  
 После вызова метода **FindFile** для получения первого файла FTP, можно вызвать [FindNextFile](#findnextfile) для получения последующих файлов FTP.  
  
### <a name="example"></a>Пример  
  См. в примере ранее в этом разделе.  
  
##  <a name="findnextfile"></a>CFtpFileFind::FindNextFile  
 Вызов этой функции-члена для продолжения поиска файла начинался с помощью вызова [FindFile](#findfile) функции-члена.  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если существует несколько файлов; нуль, если найден файл является последним элементом в каталоге или если произошла ошибка. Чтобы получить расширенные сведения об ошибке, вызовите функцию Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360). Если найден файл последний файл в каталоге или если соответствующие файлы можно найти, `GetLastError` функция возвращает ERROR_NO_MORE_FILES.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию необходимо вызывать по крайней мере один раз перед вызовом любой функции атрибутов (см. [CFileFind::FindNextFile](../../mfc/reference/cfilefind-class.md#findnextfile)).  
  
 `FindNextFile`Создает оболочку для функции Win32 [FindNextFile](http://msdn.microsoft.com/library/windows/desktop/aa364428).  
  
### <a name="example"></a>Пример  
  См. в примере этого раздела.  
  
##  <a name="getfileurl"></a>CFtpFileFind::GetFileURL  
 Вызовите эту функцию-член для получения URL-адрес из указанного файла.  
  
```  
CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Путь и имя файла из универсальный указатель ресурса (URL).  
  
### <a name="remarks"></a>Примечания  
 `GetFileURL`аналогична функции-члена [CFileFind::GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath), за исключением того, что она возвращает URL-адрес в форме `ftp://moose/dir/file.txt`.  
  
## <a name="see-also"></a>См. также  
 [Класс CFileFind](../../mfc/reference/cfilefind-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)   
 [Класс CInternetFile](../../mfc/reference/cinternetfile-class.md)   
 [Класс CGopherFile](../../mfc/reference/cgopherfile-class.md)   
 [Класс CHttpFile](../../mfc/reference/chttpfile-class.md)

