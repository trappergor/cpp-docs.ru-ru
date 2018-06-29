---
title: Класс CSingleDocTemplate | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSingleDocTemplate
- AFXWIN/CSingleDocTemplate
- AFXWIN/CSingleDocTemplate::CSingleDocTemplate
dev_langs:
- C++
helpviewer_keywords:
- CSingleDocTemplate [MFC], CSingleDocTemplate
ms.assetid: 4f3a8212-81ee-48a0-ad22-e0ed7c36a391
author: mikeblome
ms.author: mblome
ms.openlocfilehash: efdd8f5b806b7e5745aed0091a2638c8592a6ecc
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079069"
---
# <a name="csingledoctemplate-class"></a>Класс CSingleDocTemplate
Определяет шаблон документа, реализующий интерфейс одного документа (SDI).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSingleDocTemplate : public CDocTemplate  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSingleDocTemplate::CSingleDocTemplate](#csingledoctemplate)|Создает объект `CSingleDocTemplate`.|  
  
## <a name="remarks"></a>Примечания  
 Приложения SDI фрейма главного окна используется для отображения документа; одновременно может быть открыт только один документ.  
  
 Шаблон документа определяет связь между три типа классов:  
  
-   Класс документа, который можно создать производный от `CDocument`.  
  
-   Класс представления отображаются данные из класса документа, перечисленных выше. Можно наследовать от этого класса `CView`, `CScrollView`, `CFormView`, или `CEditView`. (Можно также использовать `CEditView` напрямую.)  
  
-   Класс окна фрейма, который содержит представление. Для шаблона документа SDI, могут наследовать от этого класса `CFrameWnd`, если не нужно настраивать поведение главного фрейма окна, можно использовать `CFrameWnd` напрямую без создания собственного производного класса.  
  
 Приложения SDI обычно поддерживает один тип документа, поэтому он содержит только один `CSingleDocTemplate` объекта. Одновременно может быть открыт только один документ.  
  
 Не нужно вызвать любой член функции `CSingleDocTemplate` конструктора, за исключением. Дескрипторы framework `CSingleDocTemplate` внутри объектов.  
  
 Дополнительные сведения об использовании `CSingleDocTemplate`, в разделе [шаблоны документов и процесс создания документов и представлений](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
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
 *nIDResource*  
 Указывает идентификатор ресурсы, используемые с типом документа. Это может включать меню, значок, таблицу сочетаний клавиш и строковые ресурсы.  
  
 Строковый ресурс состоит из до семи подстроки, разделенных знаком «\n» (символ «\n» требуется как заполнитель, если подстрока не включено; конечные символы «\n» не нужны); Эти подстроки описания типа документа. Сведения о подстроках, см. в разделе [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Этот строковый ресурс находится в файле ресурсов приложения. Пример:  
  
 `// MYCALC.RC`  
  
 `STRINGTABLE PRELOAD DISCARDABLE`  
  
 `BEGIN`  
  
 `IDR_MAINFRAME "MyCalc Windows Application\nSheet\nWorksheet\n Worksheets (*.myc)\n.myc\nMyCalcSheet\n MyCalc Worksheet"`  
  
 `END`  
  
 Можно изменить эту строку, с помощью редактора; вся строка отображается как единственная запись в редакторе строку не как семь отдельные записи.  
  
 Дополнительные сведения об этих типах ресурсов см. в разделе [редактора строк](../../windows/string-editor.md).  
  
 *pDocClass*  
 Указывает `CRuntimeClass` объекта класса документа. Этот класс является `CDocument`-производный класс, определенный для представления документов.  
  
 *pFrameClass*  
 Указывает на `CRuntimeClass` объект класс окна фрейма. Этот класс может быть `CFrameWnd`-производного класса, или он может быть `CFrameWnd` себя, если требуется поведение по умолчанию для главного окна фрейма.  
  
 *pViewClass*  
 Указывает `CRuntimeClass` объекта класса представления. Этот класс является `CView`-производный класс, определяемый для отображения документов.  
  
### <a name="remarks"></a>Примечания  
 Динамически выделять `CSingleDocTemplate` и передать его на `CWinApp::AddDocTemplate` из `InitInstance` функцию-член класса приложения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocViewSDI#13](../../mfc/codesnippet/cpp/csingledoctemplate-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocViewSDI#14](../../mfc/codesnippet/cpp/csingledoctemplate-class_2.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC DOCKTOOL ПОКАЗАНА](../../visual-cpp-samples.md)   
 [CDocTemplate-класс](../../mfc/reference/cdoctemplate-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDocTemplate-класс](../../mfc/reference/cdoctemplate-class.md)   
 [CDocument-класс](../../mfc/reference/cdocument-class.md)   
 [CFrameWnd-класс](../../mfc/reference/cframewnd-class.md)   
 [Класс CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md)   
 [CView-класс](../../mfc/reference/cview-class.md)   
 [Класс CWinApp](../../mfc/reference/cwinapp-class.md)
