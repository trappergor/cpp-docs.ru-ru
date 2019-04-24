---
title: Класс CSingleDocTemplate
ms.date: 11/04/2016
f1_keywords:
- CSingleDocTemplate
- AFXWIN/CSingleDocTemplate
- AFXWIN/CSingleDocTemplate::CSingleDocTemplate
helpviewer_keywords:
- CSingleDocTemplate [MFC], CSingleDocTemplate
ms.assetid: 4f3a8212-81ee-48a0-ad22-e0ed7c36a391
ms.openlocfilehash: 4d1361734f38d903e2171839b95888863126974a
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58771701"
---
# <a name="csingledoctemplate-class"></a>Класс CSingleDocTemplate

Определяет шаблон документа, реализующий интерфейс одного документа (SDI).

## <a name="syntax"></a>Синтаксис

```
class CSingleDocTemplate : public CDocTemplate
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CSingleDocTemplate::CSingleDocTemplate](#csingledoctemplate)|Создает объект `CSingleDocTemplate`.|

## <a name="remarks"></a>Примечания

SDI приложением фрейма главного окна для отображения документа; одновременно может быть открыт только один документ.

Шаблон документа определяет связь между три типа классов:

- Класс документа, который вы наследуете от `CDocument`.

- Класс представления, который отображает данные из класса документа, перечисленных выше. Можно наследовать этот класс из `CView`, `CScrollView`, `CFormView`, или `CEditView`. (Можно также использовать `CEditView` напрямую.)

- Класс окна фрейма, который содержит представление. SDI шаблона документа, можно создавать производные этого класса из `CFrameWnd`; Если не нужно настраивать поведение части главного фрейма окна, можно использовать `CFrameWnd` напрямую без создания собственного производного класса.

Обычно приложения SDI поддерживает один тип документа, поэтому он содержит только один `CSingleDocTemplate` объекта. Одновременно может быть открыт только один документ.

Не нужно вызывать любой член функции `CSingleDocTemplate` конструктора, за исключением. Дескрипторы framework `CSingleDocTemplate` внутри объектов.

Дополнительные сведения об использовании `CSingleDocTemplate`, см. в разделе [шаблоны документов и процесс создания документов и представлений](../../mfc/document-templates-and-the-document-view-creation-process.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)

`CSingleDocTemplate`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="csingledoctemplate"></a>  CSingleDocTemplate::CSingleDocTemplate

Создает объект `CSingleDocTemplate`.

```
CSingleDocTemplate(
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
  IDR_MAINFRAME "MyCalc Windows Application\nSheet\nWorksheet\n Worksheets (*.myc)\n.myc\nMyCalcSheet\n MyCalc Worksheet"
END
```

Можно изменить эту строку, с помощью редактора; вся строка представляется как одна запись в редакторе строку не семь отдельных записей.

Дополнительные сведения об этих типах ресурсов см. в разделе [редактор строк](../../windows/string-editor.md).

*pDocClass*<br/>
Указывает на `CRuntimeClass` объектом класса документа. Этот класс является `CDocument`-производный класс, определенный для представления документов.

*pFrameClass*<br/>
Указывает на `CRuntimeClass` объект класс окна фрейма. Этот класс может быть `CFrameWnd`-производного класса, или он может быть `CFrameWnd` сам, если требуется поведение по умолчанию для окна главного фрейма.

*pViewClass*<br/>
Указывает на `CRuntimeClass` объекта класса представления. Этот класс является `CView`-производный класс, определенный для отображения документов.

### <a name="remarks"></a>Примечания

Динамически выделять `CSingleDocTemplate` объект и передать его в `CWinApp::AddDocTemplate` из `InitInstance` функцию-член класса приложения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocViewSDI#13](../../mfc/codesnippet/cpp/csingledoctemplate-class_1.cpp)]

[!code-cpp[NVC_MFCDocViewSDI#14](../../mfc/codesnippet/cpp/csingledoctemplate-class_2.cpp)]

## <a name="see-also"></a>См. также

[Пример MFC DOCKTOOL ПОКАЗАНА](../../overview/visual-cpp-samples.md)<br/>
[Класс CDocTemplate](../../mfc/reference/cdoctemplate-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDocTemplate](../../mfc/reference/cdoctemplate-class.md)<br/>
[Класс CDocument](../../mfc/reference/cdocument-class.md)<br/>
[Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)<br/>
[Класс CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md)<br/>
[Класс CView](../../mfc/reference/cview-class.md)<br/>
[Класс CWinApp](../../mfc/reference/cwinapp-class.md)
