---
title: Класс CCommandLineInfo
ms.date: 11/04/2016
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
ms.openlocfilehash: 6e4b535da00fdcecf4ce52fad696cb5d2bc55efa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408151"
---
# <a name="ccommandlineinfo-class"></a>Класс CCommandLineInfo

Помогает в синтаксическом разборе командной строки при запуске приложения.

## <a name="syntax"></a>Синтаксис

```
class CCommandLineInfo : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CCommandLineInfo::CCommandLineInfo](#ccommandlineinfo)|Создает значение по умолчанию `CCommandLineInfo` объекта.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CCommandLineInfo::ParseParam](#parseparam)|Переопределите этот обратный вызов для синтаксического анализа отдельных параметров.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CCommandLineInfo::m_bRunAutomated](#m_brunautomated)|Указывает, командной строки `/Automation` обнаружен параметр.|
|[CCommandLineInfo::m_bRunEmbedded](#m_brunembedded)|Указывает, командной строки `/Embedding` обнаружен параметр.|
|[CCommandLineInfo::m_bShowSplash](#m_bshowsplash)|Указывает, должен ли отображаться экран-заставку.|
|[CCommandLineInfo::m_nShellCommand](#m_nshellcommand)|Указывает команды оболочки для обработки.|
|[CCommandLineInfo::m_strDriverName](#m_strdrivername)|Указывает драйвер имя, если команда оболочки — печати; в противном случае — пустой.|
|[CCommandLineInfo::m_strFileName](#m_strfilename)|Указывает имя файла, чтобы открыть или печати; пустой, если команда оболочки New или DDE.|
|[CCommandLineInfo::m_strPortName](#m_strportname)|Указывает порт имя, если команда оболочки — печати; в противном случае — пустой.|
|[CCommandLineInfo::m_strPrinterName](#m_strprintername)|Указывает принтеру имя, если команда оболочки — печати; в противном случае — пустой.|
|[CCommandLineInfo::m_strRestartIdentifier](#m_strrestartidentifier)|Указывает идентификатор уникальный перезапуска диспетчера перезапуска, если диспетчер перезапуска перезапуске приложения.|

## <a name="remarks"></a>Примечания

Приложения MFC обычно создает локальный экземпляр этого класса в [InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) функция его объекта приложения. Этот объект затем передается [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline), которое многократно вызывает [ParseParam](#parseparam) для заполнения `CCommandLineInfo` объекта. `CCommandLineInfo` Объект затем передается [CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand) для обработки аргументов командной строки и флаги.

Этот объект можно использовать для инкапсуляции следующие параметры командной строки и параметры:

|Аргумент командной строки|Выполняемая команда|
|----------------------------|----------------------|
|*app*|Новый файл.|
|*приложение* имя файла|Открыть файл.|
|*приложение* `/p` имя файла|Печать файла на принтер по умолчанию.|
|*приложение* `/pt` порт драйвер принтера имя файла|Печать файла на указанном принтере.|
|*Приложение* `/dde`|Запустите и ожидать команд DDE.|
|*Приложение* `/Automation`|Запуск как сервера автоматизации OLE.|
|*Приложение* `/Embedding`|Запуск изменение встроенного элемента OLE.|
|*Приложение* `/Register`<br /><br /> *Приложение* `/Regserver`|Сообщает приложению выполнения задач регистрации.|
|*Приложение* `/Unregister`<br /><br /> *Приложение* `/Unregserver`|Информирует приложение для выполнения задач, отмены регистрации.|

Создании нового производного класса от `CCommandLineInfo` обрабатывать остальные флаги и значения параметров. Переопределить [ParseParam](#parseparam) обрабатывать новые флаги.

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

По умолчанию используется для отображения на экране-заставке ( `m_bShowSplash=TRUE`) и для выполнения этой команды в меню "файл" ( `m_nShellCommand` **= NewFile**).

Приложение вызывает framework [ParseParam](#parseparam) для заполнения данных члены этого объекта.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#54](../../mfc/codesnippet/cpp/ccommandlineinfo-class_1.cpp)]

##  <a name="m_brunautomated"></a>  CCommandLineInfo::m_bRunAutomated

Указывает, что `/Automation` флаг был найден в командной строке.

```
BOOL m_bRunAutomated;
```

### <a name="remarks"></a>Примечания

Если значение равно TRUE, это означает, запускаются как сервера автоматизации OLE.

##  <a name="m_brunembedded"></a>  CCommandLineInfo::m_bRunEmbedded

Указывает, что `/Embedding` флаг был найден в командной строке.

```
BOOL m_bRunEmbedded;
```

### <a name="remarks"></a>Примечания

Если значение равно TRUE, это означает, запускаются для редактирования встроенного элемента OLE.

##  <a name="m_bshowsplash"></a>  CCommandLineInfo::m_bShowSplash

Указывает, что должно отображаться на экране-заставке.

```
BOOL m_bShowSplash;
```

### <a name="remarks"></a>Примечания

Если значение равно TRUE, это означает, что на экране-заставке для этого приложения, которые следует отображать во время запуска. Реализация по умолчанию [ParseParam](#parseparam) присваивается значение TRUE, если этот элемент данных [m_nShellCommand](#m_nshellcommand) равен `CCommandLineInfo::FileNew`.

##  <a name="m_nshellcommand"></a>  CCommandLineInfo::m_nShellCommand

Указывает команды оболочки для этого экземпляра приложения.

```
m_nShellCommand;
```

### <a name="remarks"></a>Примечания

Тип для этого элемента данных — следующий тип перечисления, который определен в `CCommandLineInfo` класса.

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

Краткое описание этих значений см. в следующем списке.

- `CCommandLineInfo::FileNew` Указывает, что имя файла не было найдено в командной строке.

- `CCommandLineInfo::FileOpen` Указывает, что имя файла была найдена в командной строке, и что ни один из флагов не найдены в командной строке: `/p`, `/pt`, `/dde`.

- `CCommandLineInfo::FilePrint` Указывает, что `/p` флаг был найден в командной строке.

- `CCommandLineInfo::FilePrintTo` Указывает, что `/pt` флаг был найден в командной строке.

- `CCommandLineInfo::FileDDE` Указывает, что `/dde` флаг был найден в командной строке.

- `CCommandLineInfo::AppRegister` Указывает, что `/Register` или `/Regserver` флаг был найден в командной строке, и приложение было предложено зарегистрироваться.

- `CCommandLineInfo::AppUnregister` Указывает, что `/Unregister` или `/Unregserver` приложения получен запрос на регистрацию.

- `CCommandLineInfo::RestartByRestartManager` Указывает, что приложение было перезапущено диспетчером перезапуска.

- `CCommandLineInfo::FileNothing` Отключает отображение новое дочернее MDI окно при запуске. По умолчанию при запуске приложения MDI, созданные мастером приложения отображается новое дочернее окно. Чтобы отключить эту функцию, приложение может использовать `CCommandLineInfo::FileNothing` как команды оболочки, при вызове [ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand). `ProcessShellCommand` вызывается `InitInstance( )` всех `CWinApp` производных классов.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#55](../../mfc/codesnippet/cpp/ccommandlineinfo-class_2.cpp)]

##  <a name="m_strdrivername"></a>  CCommandLineInfo::m_strDriverName

Сохраняет значение третьего параметра без флага в командной строке.

```
CString m_strDriverName;
```

### <a name="remarks"></a>Примечания

Этот параметр обычно является имя драйвера принтера для печати на команду оболочки. Реализация по умолчанию [ParseParam](#parseparam) задает этот только если член данных `/pt` флаг был найден в командной строке.

##  <a name="m_strfilename"></a>  CCommandLineInfo::m_strFileName

Сохраняет значение первого параметра без флага в командной строке.

```
CString m_strFileName;
```

### <a name="remarks"></a>Примечания

Этот параметр обычно является имя открываемого файла.

##  <a name="m_strportname"></a>  CCommandLineInfo::m_strPortName

Сохраняет значение четвертого параметра без флага в командной строке.

```
CString m_strPortName;
```

### <a name="remarks"></a>Примечания

Этот параметр обычно является имя порта принтера для печати на команду оболочки. Реализация по умолчанию [ParseParam](#parseparam) задает этот только если член данных `/pt` флаг был найден в командной строке.

##  <a name="m_strprintername"></a>  CCommandLineInfo::m_strPrinterName

Сохраняет значение второго параметра без флага в командной строке.

```
CString m_strPrinterName;
```

### <a name="remarks"></a>Примечания

Этот параметр обычно является имя принтера для печати на команду оболочки. Реализация по умолчанию [ParseParam](#parseparam) задает этот только если член данных `/pt` флаг был найден в командной строке.

##  <a name="m_strrestartidentifier"></a>  CCommandLineInfo::m_strRestartIdentifier

Уникальный перезапустите идентификатор в командной строке.

```
CString m_strRestartIdentifier;
```

### <a name="remarks"></a>Примечания

Перезапуск идентификатор уникален для каждого экземпляра приложения.

Если диспетчер перезапуска завершает работу приложения и настраивается на перезапуск, он, диспетчер перезапуска выполняет приложение из командной строки с идентификатором перезапуска как необязательный параметр. Когда диспетчер перезапуска использует идентификатор перезапуска, приложение можно открыть ранее открытые документы и восстанавливать файлы, автоматическое сохранение.

##  <a name="parseparam"></a>  CCommandLineInfo::ParseParam

Платформа вызывает эту функцию для синтаксического анализа и интерпретации отдельных параметров из командной строки. Вторая версия отличающимся от первого только в проектах Юникода.

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

*pszParam*<br/>
Параметр или флаг.

*bFlag*<br/>
Указывает, является ли *pszParam* параметром или флаг.

*bLast*<br/>
Указывает, если это последний параметр или флаг в командной строке.

### <a name="remarks"></a>Примечания

[CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline) вызовы `ParseParam` один раз для каждого параметра или флаг в командной строке, передав аргумент *pszParam*. Если первый символ параметра " **-** «или» **/**", он будет удален и *bFlag* имеет значение TRUE. При синтаксическом анализе последний параметр, *bLast* имеет значение TRUE.

Реализация по умолчанию эта функция распознает следующие флаги: `/p`, `/pt`, `/dde`, `/Automation`, и `/Embedding`, как показано в следующей таблице:

|Аргумент командной строки|Выполняемая команда|
|----------------------------|----------------------|
|*app*|Новый файл.|
|*приложение* имя файла|Открыть файл.|
|*приложение* `/p` имя файла|Печать файла на принтер по умолчанию.|
|*приложение* `/pt` порт драйвер принтера имя файла|Печать файла на указанном принтере.|
|*Приложение* `/dde`|Запустите и ожидать команд DDE.|
|*Приложение* `/Automation`|Запуск как сервера автоматизации OLE.|
|*Приложение* `/Embedding`|Запуск изменение встроенного элемента OLE.|
|*Приложение* `/Register`<br /><br /> *Приложение* `/Regserver`|Сообщает приложению выполнения задач регистрации.|
|*Приложение* `/Unregister`<br /><br /> *Приложение* `/Unregserver`|Информирует приложение для выполнения задач, отмены регистрации.|

Эти сведения хранятся в [m_bRunAutomated](#m_brunautomated), [m_bRunEmbedded](#m_brunembedded), и [m_nShellCommand](#m_nshellcommand). Флаги, помечены либо прямая косая черта " **/**«или дефиса» **-**".

Реализация по умолчанию помещает первый параметр без флага в [m_strFileName](#m_strfilename). В случае использования `/pt` флаг, реализация по умолчанию помещает второй, третий и четвертый параметры без флага в [m_strPrinterName](#m_strprintername), [m_strDriverName](#m_strdrivername), и [m_ strPortName](#m_strportname), соответственно.

Реализация по умолчанию также задает [m_bShowSplash](#m_bshowsplash) значение TRUE только в случае нового файла. В случае новый файл он были предприняты никакие меры, связанные с самим приложением. В любой другой вариант, включая Открытие существующих файлов с помощью оболочки действие пользователя включает в себя файл напрямую. В основе которых лежат документы точки зрения экран-заставка не нужно объявить о запуске приложения.

Переопределите эту функцию в производном классе для обработки других флаг и значения параметров.

## <a name="see-also"></a>См. также

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline)<br/>
[CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)
