---
title: "Класс CMultiDocTemplate | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMultiDocTemplate
dev_langs:
- C++
helpviewer_keywords:
- MDI, template
- CMultiDocTemplate class
ms.assetid: 5b8aa328-e461-41d0-b388-00594535e119
caps.latest.revision: 21
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
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 6e58325cd4dcaec01bf8a76006bb397fccd9a171
ms.lasthandoff: 02/24/2017

---
# <a name="cmultidoctemplate-class"></a>Класс CMultiDocTemplate
Определяет шаблон документа, реализующий многодокументный интерфейс (MDI).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMultiDocTemplate : public CDocTemplate  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMultiDocTemplate::CMultiDocTemplate](#cmultidoctemplate)|Создает объект `CMultiDocTemplate`.|  
  
## <a name="remarks"></a>Примечания  
 Приложение MDI использует фрейма главного окна в качестве рабочей области, в которой пользователь может открыть ноль или более окна фрейма документа, каждый из которых отображает документ. Более подробное описание интерфейса MDI см. в разделе *Windows интерфейс рекомендации по разработке программного обеспечения*.  
  
 Шаблон документа определяет отношения между три типа классов:  
  
-   Класс документа, который необходимо наследовать от [CDocument](../../mfc/reference/cdocument-class.md).  
  
-   Класс представления отображает данные из класса документа, перечисленных выше. Можно наследовать этот класс из [CView](../../mfc/reference/cview-class.md), `CScrollView`, `CFormView`, или `CEditView`. (Можно также использовать `CEditView` напрямую.)  
  
-   Класс фрейм окна, который содержит представление. Шаблона документа MDI, необходимо наследовать от этого класса `CMDIChildWnd`, или, если не нужно настраивать поведение окна фрейма документа, можно использовать [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) напрямую без создания собственного производного класса.  
  
 Приложение MDI может поддерживать несколько типов документов и документы различных типов могут быть открыты одновременно. Приложение имеет один шаблон документа для каждого типа документа, который он поддерживает. Например, если приложение MDI поддерживает электронных таблиц и текстовых документов, приложение имеет два `CMultiDocTemplate` объектов.  
  
 Приложение использует шаблоны документов, когда пользователь создает новый документ. Если приложение поддерживает несколько типов документов, платформа получает имена типов поддерживаемых документов из шаблонов документов и отображает их в списке в диалоговом окне новый файл. После выбора типа документа приложение создает объект класса документа, объект окна фрейма и объект представления и присоединяет их друг с другом.  
  
 Необходимо вызвать любой член функции `CMultiDocTemplate` конструктора, за исключением. Дескрипторы framework `CMultiDocTemplate` внутри объектов.  
  
 Дополнительные сведения о `CMultiDocTemplate`, в разделе [шаблоны документов и процесс создания документов и представлений](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)  
  
 `CMultiDocTemplate`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="a-namecmultidoctemplatea--cmultidoctemplatecmultidoctemplate"></a><a name="cmultidoctemplate"></a>CMultiDocTemplate::CMultiDocTemplate  
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
 Указывает идентификатор ресурсов, используемых с типом документа. Это может включать меню, значок, таблицы сочетаний клавиш и строковые ресурсы.  
  
 Строковый ресурс состоит из до семи подстрок, разделенных символом «\n» (символ «\n» требуется как местозаполнитель, если подстрока не включено; тем не менее, конечные символы «\n» не обязательны); Эти подстроки описания типа документа. Сведения о подстроках разделе [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Этот строковый ресурс находится в файле ресурсов приложения. Пример:  
  
 `// MYCALC.RC`  
  
 `STRINGTABLE PRELOAD DISCARDABLE`  
  
 `BEGIN`  
  
 `IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"`  
  
 `END`  
  
 Обратите внимание, что строка начинается со знака «\n»; Это вызвано первую подстроку не используется в приложениях MDI и поэтому не включено. Можно изменить эту строку в редакторе строк; вся строка представляется как одна запись в редакторе строк не семь отдельные записи.  
  
 Дополнительные сведения об этих типах ресурсов см. в разделе [редакторы ресурсов](../../windows/resource-editors.md).  
  
 `pDocClass`  
 Указывает `CRuntimeClass` объекта класса документа. Этот класс является **CDocument**-производный класс, определенный для представления документов.  
  
 `pFrameClass`  
 Указывает `CRuntimeClass` объекта класса окна фрейма. Этот класс может быть `CMDIChildWnd`-производного класса, или он может быть `CMDIChildWnd` себя, если требуется поведение по умолчанию для окна фрейма документа.  
  
 `pViewClass`  
 Указывает `CRuntimeClass` объекта класса представления. Этот класс является `CView`-производного класса можно определить для отображения документов.  
  
### <a name="remarks"></a>Примечания  
 Динамически выделить один `CMultiDocTemplate` объект для каждого типа документа, который поддерживает приложения и передайте каждую из них для `CWinApp::AddDocTemplate` из `InitInstance` функции-члена класса приложения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#92;](../../mfc/codesnippet/cpp/cmultidoctemplate-class_1.cpp)]  
  
 Вот во втором примере.  
  
 [!code-cpp[NVC_MFCDocView&#93;](../../mfc/codesnippet/cpp/cmultidoctemplate-class_2.cpp)]  
  
## <a name="see-also"></a>См. также  
 [CDocTemplate-класс](../../mfc/reference/cdoctemplate-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDocTemplate-класс](../../mfc/reference/cdoctemplate-class.md)   
 [Класс CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md)   
 [CWinApp-класс](../../mfc/reference/cwinapp-class.md)

