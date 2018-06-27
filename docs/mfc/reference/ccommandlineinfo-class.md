---
title: Класс CCommandLineInfo | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCommandLineInfo
- AFXWIN/CCommandLineInfo
- AFXWIN/CCommandLineInfo::CCommandLineInfo
- AFXWIN/CCommandLineInfo::ParseParam
- AFXWIN/CCommandLineInfo::m_bRunAutomated
- AFXWIN/CCommandLineInfo::m_bRunEmbedded
- AFXWIN/CCommandLineInfo::m_bShowSplash
- AFXWIN/CCommandLineInfo::m_nShellCommand
- AFXWIN/CCommandLineInfo::m_strDriverName
- AFXWIN/CCommandLineInfo::m_strFileName
- AFXWIN/CCommandLineInfo::m_strPortName
- AFXWIN/CCommandLineInfo::m_strPrinterName
- AFXWIN/CCommandLineInfo::m_strRestartIdentifier
dev_langs:
- C++
helpviewer_keywords:
- CCommandLineInfo [MFC], CCommandLineInfo
- CCommandLineInfo [MFC], ParseParam
- CCommandLineInfo [MFC], m_bRunAutomated
- CCommandLineInfo [MFC], m_bRunEmbedded
- CCommandLineInfo [MFC], m_bShowSplash
- CCommandLineInfo [MFC], m_nShellCommand
- CCommandLineInfo [MFC], m_strDriverName
- CCommandLineInfo [MFC], m_strFileName
- CCommandLineInfo [MFC], m_strPortName
- CCommandLineInfo [MFC], m_strPrinterName
- CCommandLineInfo [MFC], m_strRestartIdentifier
ms.assetid: 3e313ddb-0a82-4991-87ac-a27feff4668c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d292c3f48f0a375fbd914cf287f1e8d2cef5c6c3
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952389"
---
# <a name="ccommandlineinfo-class"></a>Класс CCommandLineInfo
Помогает в синтаксическом разборе командной строки при запуске приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CCommandLineInfo : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CCommandLineInfo::CCommandLineInfo](#ccommandlineinfo)|Создает значение по умолчанию `CCommandLineInfo` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CCommandLineInfo::ParseParam](#parseparam)|Переопределите этот обратный вызов для анализа отдельных параметров.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CCommandLineInfo::m_bRunAutomated](#m_brunautomated)|Указывает командную строку `/Automation` параметр был найден.|  
|[CCommandLineInfo::m_bRunEmbedded](#m_brunembedded)|Указывает командную строку `/Embedding` параметр был найден.|  
|[CCommandLineInfo::m_bShowSplash](#m_bshowsplash)|Указывает, должны ли отображаться экран-заставку.|  
|[CCommandLineInfo::m_nShellCommand](#m_nshellcommand)|Указывает команды оболочки для обработки.|  
|[CCommandLineInfo::m_strDriverName](#m_strdrivername)|Указывает, драйвер имя, если команда shell — печати; в противном случае — пустой.|  
|[CCommandLineInfo::m_strFileName](#m_strfilename)|Указывает имя файла, который требуется открыть или печати; пустой, если новый "или" DDE командной оболочки.|  
|[CCommandLineInfo::m_strPortName](#m_strportname)|Указывает порт имя, если команда shell — печати; в противном случае — пустой.|  
|[CCommandLineInfo::m_strPrinterName](#m_strprintername)|Указывает, что принтер имя, если команда shell — печати; в противном случае — пустой.|  
|[CCommandLineInfo::m_strRestartIdentifier](#m_strrestartidentifier)|Указывает идентификатор уникальный перезапуска диспетчера перезапуска диспетчера перезапуска перезапуска приложения.|  
  
## <a name="remarks"></a>Примечания  
 Приложения MFC обычно будет создан локальный экземпляр этого класса в [InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) функция объекта приложения. Этот объект затем передается [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline), многократно вызывает [ParseParam](#parseparam) для заполнения `CCommandLineInfo` объекта. `CCommandLineInfo` Объект затем передается [CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand) для обработки аргументов командной строки и флаги.  
  
 Этот объект можно использовать для инкапсуляции следующие параметры командной строки и параметры:  
  
|Аргумент командной строки|Команда выполнена|  
|----------------------------|----------------------|  
|*app*|Новый файл.|  
|*приложение* имя файла|Открытие файла.|  
|*приложение* `/p` имя файла|Файл печати на принтер по умолчанию.|  
|*приложение* `/pt` порт драйвера принтера имя файла|Печать файла на указанном принтере.|  
|*приложения* `/dde`|Запуск и ожидает команды DDE.|  
|*приложения* `/Automation`|Запускаются как сервер OLE-автоматизации.|  
|*приложения* `/Embedding`|Запустите изменение встроенного элемента OLE.|  
|*приложения* `/Register`<br /><br /> *приложения* `/Regserver`|Информирует приложение для выполнения любых задач регистрации.|  
|*приложения* `/Unregister`<br /><br /> *приложения* `/Unregserver`|Информирует приложение для выполнения любых задач Отмена регистрации.|  
  
 Создайте новый класс, наследующий `CCommandLineInfo` обрабатывать остальные флаги и значения параметров. Переопределить [ParseParam](#parseparam) для обработки новых флаги.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CCommandLineInfo`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="ccommandlineinfo"></a>  CCommandLineInfo::CCommandLineInfo  
 Этот конструктор создает `CCommandLineInfo` объекта со значениями по умолчанию.  
  
```  
CCommandLineInfo();
```  
  
### <a name="remarks"></a>Примечания  
 Значение по умолчанию — Показать заставку ( `m_bShowSplash=TRUE`) и для выполнения этой команды в меню «файл» ( `m_nShellCommand` **= NewFile**).  
  
 Приложение вызывает framework [ParseParam](#parseparam) для заполнения элементов данных этого объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#54](../../mfc/codesnippet/cpp/ccommandlineinfo-class_1.cpp)]  
  
##  <a name="m_brunautomated"></a>  CCommandLineInfo::m_bRunAutomated  
 Указывает, что `/Automation` флаг был найден в командной строке.  
  
```  
BOOL m_bRunAutomated;  
```  
  
### <a name="remarks"></a>Примечания  
 Если `TRUE`, это означает, что запущен как сервер OLE-автоматизации.  
  
##  <a name="m_brunembedded"></a>  CCommandLineInfo::m_bRunEmbedded  
 Указывает, что `/Embedding` флаг был найден в командной строке.  
  
```  
BOOL m_bRunEmbedded;  
```  
  
### <a name="remarks"></a>Примечания  
 Если `TRUE`, это означает, что запущен для редактирования встроенного элемента OLE.  
  
##  <a name="m_bshowsplash"></a>  CCommandLineInfo::m_bShowSplash  
 Задает отображение экрана-заставки.  
  
```  
BOOL m_bShowSplash;  
```  
  
### <a name="remarks"></a>Примечания  
 Если `TRUE`, это означает экрана-заставки для этого приложения должен отображаться во время запуска. Реализация по умолчанию [ParseParam](#parseparam) задает этого элемента данных `TRUE` Если [m_nShellCommand](#m_nshellcommand) равен `CCommandLineInfo::FileNew`.  
  
##  <a name="m_nshellcommand"></a>  CCommandLineInfo::m_nShellCommand  
 Указывает команды оболочки для этого экземпляра приложения.  
  
```  
m_nShellCommand;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип для этого элемента данных является следующий перечисляемого типа, который определен в `CCommandLineInfo` класса.  
  
```  
enum {  
    FileNew,
    FileOpen,
    FilePrint,
    FilePrintTo,
    FileDDE,
    AppRegister,
    AppUnregister,
    RestartByRestartManager,
    FileNothing = -1  
    };  
```  
  
 Краткое описание этих значений см. в списке ниже.  
  
- `CCommandLineInfo::FileNew` Указывает, что имя файла не найдено в командной строке.  
  
- `CCommandLineInfo::FileOpen` Указывает, что найдено имя файла в командной строке, и что ни один из следующих флагов были обнаружены в командной строке: `/p`, `/pt`, `/dde`.  
  
- `CCommandLineInfo::FilePrint` Указывает, что `/p` флаг был найден в командной строке.  
  
- `CCommandLineInfo::FilePrintTo` Указывает, что `/pt` флаг был найден в командной строке.  
  
- `CCommandLineInfo::FileDDE` Указывает, что `/dde` флаг был найден в командной строке.  
  
- `CCommandLineInfo::AppRegister` Указывает, что `/Register` или `/Regserver` флаг был найден в командной строке, и приложение получил запрос для регистрации.  
  
- `CCommandLineInfo::AppUnregister` Указывает, что `/Unregister` или `/Unregserver` приложения получил запрос на регистрацию.  
  
- `CCommandLineInfo::RestartByRestartManager` Указывает, что перезапуска приложения, диспетчер перезапуска.  
  
- `CCommandLineInfo::FileNothing` Отключает отображение новое дочернее MDI окно при запуске. Разработчиками предусмотрено создаваемые мастером приложений MDI-приложения при запуске отображается новое дочернее окно. Чтобы отключить эту функцию, приложение может использовать `CCommandLineInfo::FileNothing` командной оболочки, при вызове [ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand). `ProcessShellCommand` вызывается методом `InitInstance( )` всех `CWinApp` производных классов.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#55](../../mfc/codesnippet/cpp/ccommandlineinfo-class_2.cpp)]  
  
##  <a name="m_strdrivername"></a>  CCommandLineInfo::m_strDriverName  
 Сохраняет значение третьего параметра без флага в командной строке.  
  
```  
CString m_strDriverName;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот параметр обычно является имя драйвера принтера для печати на команду оболочки. Реализация по умолчанию [ParseParam](#parseparam) этот только если элемент данных задает `/pt` флаг был найден в командной строке.  
  
##  <a name="m_strfilename"></a>  CCommandLineInfo::m_strFileName  
 Сохраняет значение первого параметра без флага в командной строке.  
  
```  
CString m_strFileName;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот параметр обычно является имя открываемого файла.  
  
##  <a name="m_strportname"></a>  CCommandLineInfo::m_strPortName  
 Сохраняет значение без флага четвертого параметра в командной строке.  
  
```  
CString m_strPortName;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот параметр обычно является имя порта принтера для печати на команду оболочки. Реализация по умолчанию [ParseParam](#parseparam) этот только если элемент данных задает `/pt` флаг был найден в командной строке.  
  
##  <a name="m_strprintername"></a>  CCommandLineInfo::m_strPrinterName  
 Сохраняет значение второго параметра без флага в командной строке.  
  
```  
CString m_strPrinterName;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот параметр обычно является имя принтера для печати на команду оболочки. Реализация по умолчанию [ParseParam](#parseparam) этот только если элемент данных задает `/pt` флаг был найден в командной строке.  
  
##  <a name="m_strrestartidentifier"></a>  CCommandLineInfo::m_strRestartIdentifier  
 Уникальный перезапустите идентификатор в командной строке.  
  
```  
CString m_strRestartIdentifier;  
```  
  
### <a name="remarks"></a>Примечания  
 Перезапуск идентификатор является уникальным для каждого экземпляра приложения.  
  
 Если диспетчер перезапуска завершает работу приложения и настраивается на ее перезапуск, диспетчер перезапуска выполняет приложение из командной строки с идентификатором перезапуска как необязательный параметр. Когда диспетчер перезапуска использует идентификатор перезапуска, приложение можно повторно открыть ранее открытых документов и восстанавливать файлы автоматически сохраненная.  
  
##  <a name="parseparam"></a>  CCommandLineInfo::ParseParam  
 Платформа вызывает эту функцию для синтаксического анализа и интерпретации отдельных параметров из командной строки. Вторая версия отличается от первого только в проектах Юникода.  
  
```  
virtual void ParseParam(
    const char* pszParam,  
    BOOL bFlag,  
    BOOL bLast);

 
virtual void ParseParam(
    const TCHAR* pszParam,  
    BOOL bFlag,  
    BOOL bLast);
```  
  
### <a name="parameters"></a>Параметры  
 *pszParam*  
 Параметр или флаг.  
  
 *bFlag*  
 Указывает, является ли *pszParam* параметром или флаг.  
  
 *доменных*  
 Указывает, является ли это последний параметр или флаг в командной строке.  
  
### <a name="remarks"></a>Примечания  
 [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline) вызовы `ParseParam` один раз для каждого параметра или флаг в командной строке, передавая аргумент *pszParam*. Если первый символ параметра " **-**«или» **/**", то оно будет удалено и *bFlag* равно `TRUE`. При синтаксическом анализе последний параметр *доменных* равно `TRUE`.  
  
 Реализация по умолчанию эта функция распознает следующие флаги: `/p`, `/pt`, `/dde`, `/Automation`, и `/Embedding`, как показано в следующей таблице:  
  
|Аргумент командной строки|Команда выполнена|  
|----------------------------|----------------------|  
|*app*|Новый файл.|  
|*приложение* имя файла|Открытие файла.|  
|*приложение* `/p` имя файла|Файл печати на принтер по умолчанию.|  
|*приложение* `/pt` порт драйвера принтера имя файла|Печать файла на указанном принтере.|  
|*приложения* `/dde`|Запуск и ожидает команды DDE.|  
|*приложения* `/Automation`|Запускаются как сервер OLE-автоматизации.|  
|*приложения* `/Embedding`|Запустите изменение встроенного элемента OLE.|  
|*приложения* `/Register`<br /><br /> *приложения* `/Regserver`|Информирует приложение для выполнения любых задач регистрации.|  
|*приложения* `/Unregister`<br /><br /> *приложения* `/Unregserver`|Информирует приложение для выполнения любых задач Отмена регистрации.|  
  
 Эти сведения хранятся в [m_bRunAutomated](#m_brunautomated), [m_bRunEmbedded](#m_brunembedded), и [m_nShellCommand](#m_nshellcommand). Флаги помечены либо прямой косой черты " **/**«или дефиса» **-**".  
  
 Реализация по умолчанию помещается в первый параметр без флага [m_strFileName](#m_strfilename). В случае использования `/pt` флаг, реализация по умолчанию помещает второй, третий и четвертый параметров без флага в [m_strPrinterName](#m_strprintername), [m_strDriverName](#m_strdrivername), и [m_ strPortName](#m_strportname)соответственно.  
  
 Реализация по умолчанию также задает [m_bShowSplash](#m_bshowsplash) для `TRUE` только в случае нового файла. В случае нового файла пользователь начал операции с использованием самого приложения. В любом другом случае, включая Открытие существующих файлов с помощью командной оболочки действия пользователя включает в себя файл напрямую. В документе зрения экран-заставка не требуется объявить о запуске приложения.  
  
 Переопределите эту функцию в производном классе для обработки других флаг и значения параметров.  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline)   
 [CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)

