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
ms.openlocfilehash: 9a1b303924458ab03bc2ec42be1fbc3b2afa64ed
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566504"
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
|[CMultiDocTemplate::CMultiDocTemplate](#cmultidoctemplate)|Создает объект `CMultiDocTemplate`.|

## <a name="remarks"></a>Примечания

Приложение MDI использует фрейма главного окна в качестве рабочей области в котором пользователь может открыть ноль или несколько окон фрейма документа, каждый из которых отображает документ. Более подробное описание интерфейса MDI, см. в разделе *интерфейс Windows, касающиеся разработки программного обеспечения*.

Шаблон документа определяет отношения между три типа классов:

- Класс документа, который вы наследуете от [CDocument](../../mfc/reference/cdocument-class.md).

- Класс представления, который отображает данные из класса документа, перечисленных выше. Можно наследовать этот класс из [CView](../../mfc/reference/cview-class.md), `CScrollView`, `CFormView`, или `CEditView`. (Можно также использовать `CEditView` напрямую.)

- Класс окна фрейма, который содержит представление. Для шаблона документа MDI, можно создавать производные этого класса из `CMDIChildWnd`, или, если не нужно настраивать поведение окон фрейма документа, можно использовать [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) напрямую без создания собственного производного класса.

MDI-приложения может поддерживать более чем один тип документа, а документы различных типов могут быть открыты одновременно. Ваше приложение имеет один шаблон документа для каждого типа документа, который он поддерживает. Например, если приложение MDI поддерживает электронных таблиц и текстовых документов, приложение имеет два `CMultiDocTemplate` объектов.

Приложение использует шаблоны документов, когда пользователь создает новый документ. Если приложение поддерживает более чем один тип документа, платформа возвращает имена типов поддерживаемых документов из шаблонов документов и отображает их в списке в диалоговом окне новый файл. Когда пользователь выбрал тип документа, приложение создает объект класса документа, объект окна фрейма и объект представления и вкладывает их друг с другом.

Не обязательно вызывать любой член функции `CMultiDocTemplate` конструктора, за исключением. Дескрипторы framework `CMultiDocTemplate` внутри объектов.

Дополнительные сведения о `CMultiDocTemplate`, см. в разделе [шаблоны документов и процесс создания документов и представлений](../../mfc/document-templates-and-the-document-view-creation-process.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)

`CMultiDocTemplate`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="cmultidoctemplate"></a>  CMultiDocTemplate::CMultiDocTemplate

Создает объект `CMultiDocTemplate`.

```
CMultiDocTemplate(
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>Параметры

*nIDResource*<br/>
Указывает идентификатор ресурсы, используемые с типом документа. Это может включать меню, значок, таблицу сочетаний клавиш и строковые ресурсы.

Строковый ресурс состоит из до семи подстрок, разделенных символом '\n' ('\n' символ необходим в качестве заполнителя, если подстрока не включается; тем не менее, конечные символы '\n' не требуются); Эти подстроки описания типа документа. Сведения о подстроках, см. в разделе [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Этот строковый ресурс находится в файле ресурсов приложения. Пример:

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"
END
```

Обратите внимание, что строка начинается со знака «\n»; Это обусловлено первую подстроку не используется в приложениях MDI и поэтому не включается. Можно изменить эту строку, с помощью редактора; вся строка представляется как одна запись в редакторе строку не семь отдельных записей.

Дополнительные сведения об этих типах ресурсов см. в разделе [редакторы ресурсов](../../windows/resource-editors.md).

*pDocClass*<br/>
Указывает на `CRuntimeClass` объектом класса документа. Этот класс является `CDocument`-производный класс, определенный для представления документов.

*pFrameClass*<br/>
Указывает на `CRuntimeClass` объектом класса окна фрейма. Этот класс может быть `CMDIChildWnd`-производного класса, или он может быть `CMDIChildWnd` сам, если требуется поведение по умолчанию для вашего окна фрейма документа.

*pViewClass*<br/>
Указывает на `CRuntimeClass` объекта класса представления. Этот класс является `CView`-производный класс, определенный для отображения документов.

### <a name="remarks"></a>Примечания

Динамическое выделение таковой `CMultiDocTemplate` объект для каждого типа документа, который поддерживает приложения и передайте каждый из них до `CWinApp::AddDocTemplate` из `InitInstance` функцию-член класса приложения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#92](../../mfc/codesnippet/cpp/cmultidoctemplate-class_1.cpp)]

Вот еще один пример.

[!code-cpp[NVC_MFCDocView#93](../../mfc/codesnippet/cpp/cmultidoctemplate-class_2.cpp)]

## <a name="see-also"></a>См. также

[Класс CDocTemplate](../../mfc/reference/cdoctemplate-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDocTemplate](../../mfc/reference/cdoctemplate-class.md)<br/>
[Класс CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md)<br/>
[Класс CWinApp](../../mfc/reference/cwinapp-class.md)
