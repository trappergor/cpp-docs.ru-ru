---
title: Класс Кусертул
ms.date: 11/04/2016
f1_keywords:
- CUserTool
- AFXUSERTOOL/CUserTool
- AFXUSERTOOL/CUserTool::CopyIconToClipboard
- AFXUSERTOOL/CUserTool::DrawToolIcon
- AFXUSERTOOL/CUserTool::GetCommand
- AFXUSERTOOL/CUserTool::GetCommandId
- AFXUSERTOOL/CUserTool::Invoke
- AFXUSERTOOL/CUserTool::Serialize
- AFXUSERTOOL/CUserTool::SetCommand
- AFXUSERTOOL/CUserTool::SetToolIcon
- AFXUSERTOOL/CUserTool::LoadDefaultIcon
- AFXUSERTOOL/CUserTool::m_strArguments
- AFXUSERTOOL/CUserTool::m_strInitialDirectory
- AFXUSERTOOL/CUserTool::m_strLabel
helpviewer_keywords:
- CUserTool [MFC], CopyIconToClipboard
- CUserTool [MFC], DrawToolIcon
- CUserTool [MFC], GetCommand
- CUserTool [MFC], GetCommandId
- CUserTool [MFC], Invoke
- CUserTool [MFC], Serialize
- CUserTool [MFC], SetCommand
- CUserTool [MFC], SetToolIcon
- CUserTool [MFC], LoadDefaultIcon
- CUserTool [MFC], m_strArguments
- CUserTool [MFC], m_strInitialDirectory
- CUserTool [MFC], m_strLabel
ms.assetid: 7c287d3e-d012-488d-b4e1-aa0f83f294bb
ms.openlocfilehash: b73cb3d3c6e244a9aa41a91a3ee9ff1efa98d496
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502242"
---
# <a name="cusertool-class"></a>Класс Кусертул

Пользовательский инструмент — это пункт меню, который запускает внешнее приложение. Вкладка **средства** диалогового окна **Настройка** ( [класс кмфктулбарскустомизедиалог](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)) позволяет пользователю добавлять пользовательские средства и указывать имя, команду, аргументы и исходный каталог для каждого инструмента пользователя.

## <a name="syntax"></a>Синтаксис

```
class CUserTool : public CObject
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кусертул:: Копиконтоклипбоард](#copyicontoclipboard)||
|[Кусертул::D Равтуликон](#drawtoolicon)|Рисует значок пользовательского инструмента в указанном прямоугольнике.|
|[Кусертул:: Command](#getcommand)|Возвращает строку, содержащую текст команды, связанной с пользовательским инструментом.|
|[Кусертул:: Жеткоммандид](#getcommandid)|Возвращает идентификатор команды для пункта меню инструмента "пользователь".|
|[Кусертул:: Invoke](#invoke)|Выполняет команду, связанную с пользовательским инструментом.|
|[Кусертул:: Serialize](#serialize)|Считывает этот объект из архива или записывает в него. (Переопределяет [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|
|[Кусертул:: Сеткомманд](#setcommand)|Задает команду, связанную с пользовательским инструментом.|
|[Кусертул:: Сеттуликон](#settoolicon)|Загружает значок для пользовательского инструмента из приложения, связанного с инструментом.|

### <a name="protected-methods"></a>Защищенные методы

|name|Описание|
|----------|-----------------|
|[Кусертул:: Лоаддефаултикон](#loaddefaulticon)|Загружает значок по умолчанию для пользовательского инструмента.|

### <a name="data-members"></a>Элементы данных

|name|Описание|
|----------|-----------------|
|[Кусертул:: m_strArguments](#m_strarguments)|Аргументы командной строки для инструмента "пользователь".|
|[Кусертул:: m_strInitialDirectory](#m_strinitialdirectory)|Исходный каталог для инструмента "пользователь".|
|[Кусертул:: m_strLabel](#m_strlabel)|Имя инструмента, отображаемое в пункте меню для инструмента.|

## <a name="remarks"></a>Примечания

Дополнительные сведения о том, как включить пользовательские средства в приложении, см. в разделе [класс кусертулсманажер](../../mfc/reference/cusertoolsmanager-class.md).

## <a name="example"></a>Пример

В следующем примере показано, как создать инструмент из объекта, `CUserToolsManager` `m_strLabel` задать переменную-член и задать приложение, которое запускается пользовательским инструментом. Этот фрагмент кода является частью демонстрационного [примера Visual Studio](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#35](../../mfc/codesnippet/cpp/cusertool-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[кусертул](../../mfc/reference/cusertool-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афксусертул. h

##  <a name="copyicontoclipboard"></a>Кусертул:: Копиконтоклипбоард

Дополнительные сведения см. в исходном коде, расположенном в папке **VC\\atlmfc\\src\\mfc** каталога установки Visual Studio.

```
BOOL CopyIconToClipboard();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="drawtoolicon"></a>Кусертул::D Равтуликон

Рисует значок пользовательского инструмента в центре указанного прямоугольника.

```
void DrawToolIcon(
    CDC* pDC,
    const CRect& rectImage);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
окне Указатель на контекст устройства.

*ректимаже*<br/>
окне Задает координаты области для вывода значка.

##  <a name="getcommand"></a>Кусертул:: Command

Возвращает строку, содержащую текст команды, связанной с пользовательским инструментом.

```
const CString& GetCommand() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на `CString` объект, содержащий текст команды, связанной с пользовательским инструментом.

##  <a name="getcommandid"></a>Кусертул:: Жеткоммандид

Возвращает идентификатор команды для инструмента "пользователь".

```
UINT GetCommandId() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор команды этого инструмента пользователя.

##  <a name="invoke"></a>Кусертул:: Invoke

Выполняет команду, связанную с пользовательским инструментом.

```
virtual BOOL Invoke();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если команда выполнена успешно. в противном случае — 0.

### <a name="remarks"></a>Примечания

Вызывает [ShellExecute](/windows/win32/api/shellapi/nf-shellapi-shellexecutew) для выполнения команды, связанной с пользовательским инструментом. Функция завершается ошибкой, если команда пуста или происходит сбой [ShellExecute](/windows/win32/api/shellapi/nf-shellapi-shellexecutew) .

##  <a name="loaddefaulticon"></a>Кусертул:: Лоаддефаултикон

Загружает значок по умолчанию для пользовательского инструмента.

```
virtual HICON LoadDefaultIcon();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на загруженный значок (ХИКОН) или значение NULL, если не удается загрузить значок по умолчанию.

### <a name="remarks"></a>Примечания

Платформа вызывает этот метод, когда не удается загрузить значок для определяемого пользователем средства из исполняемого файла средства.

Переопределите этот метод, чтобы указать собственный значок инструмента по умолчанию.

##  <a name="m_strarguments"></a>Кусертул:: m_strArguments

Аргументы командной строки для инструмента "пользователь".

```
CString m_strArguments;
```

### <a name="remarks"></a>Примечания

Эта строка передается средству при вызове [кусертул:: Invoke](#invoke) или при нажатии пользователем команды, связанной с этим инструментом.

##  <a name="m_strinitialdirectory"></a>Кусертул:: m_strInitialDirectory

Указывает исходный каталог для инструмента пользователя.

```
CString m_strInitialDirectory;
```

### <a name="remarks"></a>Примечания

Эта переменная указывает исходный каталог, в котором выполняется средство, при вызове [кусертул:: Invoke](#invoke) или при нажатии пользователем команды, связанной с этим инструментом.

##  <a name="m_strlabel"></a>Кусертул:: m_strLabel

Метка, отображаемая в пункте меню для инструмента.

```
CString m_strLabel;
```

##  <a name="serialize"></a>Кусертул:: Serialize

Дополнительные сведения см. в исходном коде, расположенном в папке **VC\\atlmfc\\src\\mfc** каталога установки Visual Studio.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Параметры

[in] *ar*<br/>

### <a name="remarks"></a>Примечания

##  <a name="setcommand"></a>Кусертул:: Сеткомманд

Задает приложение, которое запускается пользовательским инструментом.

```
void SetCommand(LPCTSTR lpszCmd);
```

### <a name="parameters"></a>Параметры

*лпсзкмд*<br/>
окне Указывает новое приложение, которое будет связано с пользовательским инструментом.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы задать новое приложение, которое запускается пользовательским инструментом. Метод уничтожает старый значок и загружает новый значок из заданного приложения. Если не удается загрузить значок из приложения, он загружает значок по умолчанию для пользовательского инструмента путем вызова [кусертул:: лоаддефаултикон](#loaddefaulticon).

##  <a name="settoolicon"></a>Кусертул:: Сеттуликон

Загружает значок пользовательского инструмента из приложения, используемого средством.

```
virtual HICON SetToolIcon();
```

### <a name="return-value"></a>Возвращаемое значение

Маркер загруженного значка.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы загрузить значок, который будет отображаться в пункте меню. Этот метод выполняет поиск значка в исполняемом файле, используемом средством. Если значок по умолчанию отсутствует, вместо него используется значок, предоставленный [кусертул:: лоаддефаултикон](#loaddefaulticon) .

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CWinAppEx](../../mfc/reference/cwinappex-class.md)<br/>
[Класс CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md)
