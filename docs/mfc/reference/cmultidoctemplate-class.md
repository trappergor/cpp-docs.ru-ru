---
title: Класс CMultiDocTemplate
ms.date: 11/04/2016
f1_keywords:
- CMultiDocTemplate
- AFXWIN/CMultiDocTemplate
- AFXWIN/CMultiDocTemplate::CMultiDocTemplate
helpviewer_keywords:
- CMultiDocTemplate [MFC], CMultiDocTemplate
ms.assetid: 5b8aa328-e461-41d0-b388-00594535e119
ms.openlocfilehash: 3b3f239b05b1cf7661929333e2d616acce6bedb0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319732"
---
# <a name="cmultidoctemplate-class"></a>Класс CMultiDocTemplate

Определяет шаблон документа, реализующий многодокументный интерфейс (MDI).

## <a name="syntax"></a>Синтаксис

```
class CMultiDocTemplate : public CDocTemplate
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMultiDocTemplate::CMultiDocTemplate](#cmultidoctemplate)|Формирует объект `CMultiDocTemplate`.|

## <a name="remarks"></a>Remarks

Приложение MDI использует окно основной кадр в качестве рабочего пространства, в котором пользователь может открыть ноль или больше окон кадра документа, каждое из которых отображает документ. Более подробное описание MDI можно ознакомиться *с Руководящими принципами windows Interface для разработки программного обеспечения.*

Шаблон документа определяет отношения между тремя типами классов:

- Класс документов, который вы получаете из [CDocument](../../mfc/reference/cdocument-class.md).

- Класс представления, отображаемый данными из класса документов, перечисленных выше. Вы можете получить этот класс `CScrollView` `CFormView`из `CEditView` [CView](../../mfc/reference/cview-class.md), , или . (Вы также `CEditView` можете использовать непосредственно.)

- Класс окна кадра, который содержит представление. Для шаблона документов MDI можно `CMDIChildWnd`извлечь этот класс из, или, если вам не нужно настраивать поведение окон кадра документа, вы можете использовать [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) непосредственно без получения собственного класса.

Приложение MDI может поддерживать более одного типа документов, и документы различных типов могут быть открыты одновременно. Ваше приложение имеет один шаблон документа для каждого типа документа, который он поддерживает. Например, если приложение MDI поддерживает как электронные таблицы, так и текстовые документы, приложение имеет два `CMultiDocTemplate` объекта.

Приложение использует шаблон документа (ы), когда пользователь создает новый документ. Если приложение поддерживает более одного типа документа, то фреймворк получает имена поддерживаемых типов документов из шаблонов документов и отображает их в списке в диалоговом окне файла New. После того, как пользователь выбрал тип документа, приложение создает объект класса документа, объект окна кадра и объект представления и прикрепляет их друг к другу.

Вам не нужно вызывать какие-либо функции члена, `CMultiDocTemplate` кроме конструктора. Фрейм `CMultiDocTemplate` обрабатывает объекты внутренне.

Для получения `CMultiDocTemplate`дополнительной информации о, см. [Document Templates and the Document/View Creation Process](../../mfc/document-templates-and-the-document-view-creation-process.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)

`CMultiDocTemplate`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cmultidoctemplatecmultidoctemplate"></a><a name="cmultidoctemplate"></a>CMultiDocTemplate::CMultiDocTemplate

Формирует объект `CMultiDocTemplate`.

```
CMultiDocTemplate(
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>Параметры

*nIDResource*<br/>
Упогоняет идентификатор ресурсов, используемых с типом документа. Это может включать меню, значок, таблицу акселератора и строковые ресурсы.

Ресурс строки состоит из семи подстроек, разделенных символом 'n' (символ 'n' необходим в качестве держателя места, если подстрока не включена; однако, задние символы 'n' не являются необходимыми); эти подстроки описывают тип документа. Для получения информации о подстроках [см. CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Этот ресурс строки находится в файле ресурса приложения. Пример:

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"
END
```

Обратите внимание, что строка начинается с символа 'n'; это связано с тем, что первая подстрока не используется для приложений MDI и поэтому не включена. Эту строку можно отредконить с помощью строки редактора; вся строка отображается как одна запись в строке редактора, а не как семь отдельных записей.

Для получения дополнительной информации об этих типах ресурсов [см.](../../windows/resource-editors.md)

*pDocClass*<br/>
Указывает на `CRuntimeClass` объект класса документов. Этот класс `CDocument`— это класс, который вы определяете для представления документов.

*pFrameClass*<br/>
Указывает на `CRuntimeClass` объект класса окна кадра. Этот класс может `CMDIChildWnd`быть -производным `CMDIChildWnd` классом, или он может быть сам, если вы хотите поведение по умолчанию для окон кадра документа.

*pViewClass*<br/>
Указывает на `CRuntimeClass` объект класса представления. Этот класс `CView`является классом, который вы определяете для отображения документов.

### <a name="remarks"></a>Remarks

Динамически выделите по одному `CMultiDocTemplate` объекту для каждого `CWinApp::AddDocTemplate` типа `InitInstance` документа, который поддерживает приложение, и передайте каждый из них от функции члена класса приложения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#92](../../mfc/codesnippet/cpp/cmultidoctemplate-class_1.cpp)]

Вот второй пример.

[!code-cpp[NVC_MFCDocView#93](../../mfc/codesnippet/cpp/cmultidoctemplate-class_2.cpp)]

## <a name="see-also"></a>См. также раздел

[Класс CDocTemplate](../../mfc/reference/cdoctemplate-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDocTemplate](../../mfc/reference/cdoctemplate-class.md)<br/>
[Класс CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md)<br/>
[Класс CWinApp](../../mfc/reference/cwinapp-class.md)
