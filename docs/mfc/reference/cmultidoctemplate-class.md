---
title: "Класс CMultiDocTemplate | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMultiDocTemplate
- AFXWIN/CMultiDocTemplate
- AFXWIN/CMultiDocTemplate::CMultiDocTemplate
dev_langs:
- C++
helpviewer_keywords:
- CMultiDocTemplate [MFC], CMultiDocTemplate
ms.assetid: 5b8aa328-e461-41d0-b388-00594535e119
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6d5862a547b41ec8d359b09795f7b9985530fc97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmultidoctemplate-class"></a>Класс CMultiDocTemplate
Определяет шаблон документа, реализующий многодокументный интерфейс (MDI).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMultiDocTemplate : public CDocTemplate  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMultiDocTemplate::CMultiDocTemplate](#cmultidoctemplate)|Создает объект `CMultiDocTemplate`.|  
  
## <a name="remarks"></a>Примечания  
 Приложение MDI использует фрейма главного окна как рабочую область в котором пользователь может открыть ноль или более окна фрейма документа, каждый из которых отображает документ. Более подробное описание интерфейса MDI см. в разделе *рекомендации по интерфейсу Windows для программного проектирования*.  
  
 Шаблон документа определяет отношения между три типа классов:  
  
-   Класс документа, который можно создать производный от [CDocument](../../mfc/reference/cdocument-class.md).  
  
-   Класс представления отображаются данные из класса документа, перечисленных выше. Можно наследовать от этого класса [CView](../../mfc/reference/cview-class.md), `CScrollView`, `CFormView`, или `CEditView`. (Можно также использовать `CEditView` напрямую.)  
  
-   Класс окна фрейма, который содержит представление. Для шаблона документа MDI, могут наследовать от этого класса `CMDIChildWnd`, или, если не нужно настраивать поведение окна фрейма документа, можно использовать [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) напрямую без создания собственного производного класса.  
  
 MDI-приложения может поддерживать более чем один тип документа, а документы различных типов могут быть открыты одновременно. Ваше приложение имеет один шаблон документа для каждого типа документа, который он поддерживает. Например, если приложение MDI поддерживает электронные таблицы и текстовые документы, приложение имеет два `CMultiDocTemplate` объектов.  
  
 Приложение использует шаблоны документов, когда пользователь создает новый документ. Если приложение поддерживает более чем один тип документа, платформа получает имена типов поддерживаемых документов на основании шаблонов документов и отображает их в списке в диалоговом окне новый файл. Если пользователь выбрал тип документа, приложение создает объект класса документа, объект окна фрейма и объект представления и вкладывает их друг с другом.  
  
 Необходимо вызвать любой член функции `CMultiDocTemplate` конструктора, за исключением. Дескрипторы framework `CMultiDocTemplate` внутри объектов.  
  
 Дополнительные сведения о `CMultiDocTemplate`, в разделе [шаблоны документов и процесс создания документов и представлений](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)  
  
 `CMultiDocTemplate`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="cmultidoctemplate"></a>CMultiDocTemplate::CMultiDocTemplate  
 Создает объект `CMultiDocTemplate`.  
  
```  
CMultiDocTemplate(
    UINT nIDResource,  
    CRuntimeClass* pDocClass,  
    CRuntimeClass* pFrameClass,  
    CRuntimeClass* pViewClass);
```  
  
### <a name="parameters"></a>Параметры  
 `nIDResource`  
 Указывает идентификатор ресурсы, используемые с типом документа. Это может включать меню, значок, таблицу сочетаний клавиш и строковые ресурсы.  
  
 Строковый ресурс состоит из до семи подстроки, разделенных знаком «\n» (символ «\n», необходимое в качестве заполнителя Если подстрока не указан; конечные символы «\n» не нужны); Эти подстроки описания типа документа. Сведения о подстроках см. в разделе [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Этот строковый ресурс находится в файле ресурсов приложения. Пример:  
  
 `// MYCALC.RC`  
  
 `STRINGTABLE PRELOAD DISCARDABLE`  
  
 `BEGIN`  
  
 `IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"`  
  
 `END`  
  
 Обратите внимание, что строка начинается с символа '\n'; Это происходит потому, первая подстрока не используется в приложениях MDI и не включается. Можно изменить эту строку, с помощью редактора; вся строка отображается как единственная запись в редакторе строку не как семь отдельные записи.  
  
 Дополнительные сведения об этих типах ресурсов см. в разделе [редакторы ресурсов](../../windows/resource-editors.md).  
  
 `pDocClass`  
 Указывает `CRuntimeClass` объекта класса документа. Этот класс является **CDocument**-производный класс, определенный для представления документов.  
  
 `pFrameClass`  
 Указывает `CRuntimeClass` объекта класса окна фрейма. Этот класс может быть `CMDIChildWnd`-производного класса, или он может быть `CMDIChildWnd` себя, если требуется поведение по умолчанию для вашего окна фрейма документа.  
  
 `pViewClass`  
 Указывает `CRuntimeClass` объекта класса представления. Этот класс является `CView`-производный класс, определяемый для отображения документов.  
  
### <a name="remarks"></a>Примечания  
 Динамически выделить один `CMultiDocTemplate` объекта для каждого типа документа, который поддерживает приложения и передать каждое из них `CWinApp::AddDocTemplate` из `InitInstance` функцию-член класса приложения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#92](../../mfc/codesnippet/cpp/cmultidoctemplate-class_1.cpp)]  
  
 Вот во втором примере.  
  
 [!code-cpp[NVC_MFCDocView#93](../../mfc/codesnippet/cpp/cmultidoctemplate-class_2.cpp)]  
  
## <a name="see-also"></a>См. также  
 [CDocTemplate-класс](../../mfc/reference/cdoctemplate-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDocTemplate-класс](../../mfc/reference/cdoctemplate-class.md)   
 [Класс CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md)   
 [Класс CWinApp](../../mfc/reference/cwinapp-class.md)
