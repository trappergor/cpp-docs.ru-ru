---
title: "COleLinkingDoc Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleLinkingDoc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleLinkingDoc class"
  - "OLE containers, client items"
ms.assetid: 9f547f35-2f95-427f-b9c0-85c31940198b
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# COleLinkingDoc Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Базовый класс для документов OLE\-контейнер, которые поддерживают связывание на внедренный элементам они содержатся.  
  
## Синтаксис  
  
```  
class COleLinkingDoc : public COleDocument  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleLinkingDoc::COleLinkingDoc](../Topic/COleLinkingDoc::COleLinkingDoc.md)|Создает объект `COleLinkingDoc`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleLinkingDoc::Register](../Topic/COleLinkingDoc::Register.md)|Регистрирует документ с OLE системные библиотеки DLL.|  
|[COleLinkingDoc::Revoke](../Topic/COleLinkingDoc::Revoke.md)|Отменяет регистрацию документа.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleLinkingDoc::OnFindEmbeddedItem](../Topic/COleLinkingDoc::OnFindEmbeddedItem.md)|Находит указанный встроенный элемент.|  
|[COleLinkingDoc::OnGetLinkedItem](../Topic/COleLinkingDoc::OnGetLinkedItem.md)|Находит заданный связанный элемент.|  
  
## Заметки  
 Приложение\-контейнер, который поддерживает связывание на внедренный элементам вызвать контейнером "соединения". Пример приложения [OCLIENT](../../top/visual-cpp-samples.md) примере контейнера ссылки.  
  
 Если источник связанного элемента, внедренный элемент в другом документе, в котором содержится документ должна быть загружена, внедренный элемент, который нужно изменить.  По этой причине контейнер связи должен запускаться другим приложение\-контейнером, когда пользователь хочет изменить источник связанного элемента.  Приложение должно также использовать класс [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) для правильного создания документов started программно.  
  
 Чтобы сделать своим контейнером контейнер связи, наследуйте класс от `COleLinkingDoc` документа вместо [COleDocument](../../mfc/reference/coledocument-class.md).  Как и с любым другим OLE\-контейнер, необходимо сконструировать класс для хранения данных так же, как и встроенные или связанные элементы приложения собственных.  Кроме того, структуры, проектных данных для хранения собственные данные.  При указании `CDocItem`\- производный класс для данных приложения собственных можно использовать интерфейс указанный `COleDocument` чтобы хранить собственные данные, а также существующие данные в формате ole.  
  
 Чтобы разрешить приложение запускаться программно другим контейнером, объявите объект `COleTemplateServer` в качестве члена `CWinApp` приложения \- производный класс.  
  
 [!code-cpp[NVC_MFCOleContainer#23](../../mfc/reference/codesnippet/CPP/colelinkingdoc-class_1.h)]  
  
 В функции\-члене вашего `CWinApp`\- производном классе `InitInstance`, создайте шаблон документа и определите `COleLinkingDoc`\- производный класс как класс документа.  
  
 [!code-cpp[NVC_MFCOleContainer#24](../../mfc/reference/codesnippet/CPP/colelinkingdoc-class_2.cpp)]  
  
 Подключите объект `COleTemplateServer` к шаблонам документов, вызвав функцию\-член `ConnectTemplate` объекта и зарегистрируйте все объекты класса с OLE системой путем вызова **COleTemplateServer::RegisterAll**:  
  
 [!code-cpp[NVC_MFCOleContainer#25](../../mfc/reference/codesnippet/CPP/colelinkingdoc-class_3.cpp)]  
  
 Образец `CWinApp`\- определение производного класса, а функция `InitInstance` см. в разделе OCLIENT.H и OCLIENT.CPP в образце [OCLIENT](../../top/visual-cpp-samples.md) MFC.  
  
 Дополнительные сведения об использовании `COleLinkingDoc` см. в разделе статьи [контейнеры: Реализация контейнера](../../mfc/containers-implementing-a-container.md) и [контейнеры: Расширенные функции](../../mfc/containers-advanced-features.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CDocument](../Topic/CDocument%20Class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 `COleLinkingDoc`  
  
## Требования  
 **Header:**  afxole.h  
  
## См. также  
 [Образец OCLIENT MFC](../../top/visual-cpp-samples.md)   
 [COleDocument Class](../../mfc/reference/coledocument-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)