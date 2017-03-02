---
title: "Структура CCreateContext | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCreateContext
dev_langs:
- C++
helpviewer_keywords:
- CCreateContext structure
ms.assetid: 337a0e44-d910-49a8-afc0-c7207666a9dc
caps.latest.revision: 22
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 231f2e44e085d27a2b2cbf289adf7b0521471b0e
ms.lasthandoff: 02/24/2017

---
# <a name="ccreatecontext-structure"></a>Структура CCreateContext
Инфраструктура использует `CCreateContext` структуры при создании окна фрейма и представления, которые связаны с документом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct CCreateContext  
```  
  
## <a name="remarks"></a>Примечания  
 `CCreateContext`представляет собой структуру и не имеет базового класса.  
  
 При создании окна значений в этой структуре предоставляют сведения, используемые для соединения компонентов документа в представлении данных. Необходимо использовать `CCreateContext` при переопределении части процесса создания.  
  
 A `CCreateContext` структура содержит указатели на документ, окно области, представления и шаблон документа. Он также содержит указатель на `CRuntimeClass` , идентифицирующий тип представления для создания. Информация о классе во время выполнения и указатель текущего документа используются для динамического создания нового представления. В следующей таблице перечислены как и когда каждая `CCreateContext` член может быть использован:  
  
|Член|Тип|Что такое для|  
|------------|----------|--------------------|  
|`m_pNewViewClass`|`CRuntimeClass*`|`CRuntimeClass`для создания нового представления.|  
|`m_pCurrentDoc`|`CDocument*`|Существующий документ, который следует связать с новым представлением.|  
|`m_pNewDocTemplate`|`CDocTemplate*`|Шаблон документа, связанные с созданием нового окна области интерфейса MDI.|  
|`m_pLastView`|`CView*`|Исходное представление, на котором моделируются дополнительные представления, как создавать представления окна разделителя или создание второе представление документа.|  
|`m_pCurrentFrame`|`CFrameWnd*`|Окна фрейма, на котором дополнительной рамки окна моделируются, как создание второе окно фрейма документа.|  
  
 Когда шаблон документа создает документ и связанных с ним компонентов, он проверяет данные, хранящиеся в `CCreateContext` структуру. Например представление не следует создавать для несуществующего документа.  
  
> [!NOTE]
>  Все указатели в `CCreateContext` являются необязательными и могут быть `NULL` Если определен или неизвестно.  
  
 `CCreateContext`используется с функциями-членами, перечисленных в разделе «См.» Обратитесь к описания этих функций конкретные сведения, если вы планируете их переопределения.  
  
 Вот несколько общих рекомендаций.  
  
-   При передаче в качестве аргумента для создания окна, как и в `CWnd::Create`, `CFrameWnd::Create`, и `CFrameWnd::LoadFrame`, создать контекст указывает, что новое окно должен быть подключен к. Для большинства окон всю структуру является необязательным и `NULL` указатель может быть передан.  
  
-   Для функций-членов overridable таких как `CFrameWnd::OnCreateClient`, `CCreateContext` аргумент является необязательным.  
  
-   Для функций-членов участвующие в представлении создания, необходимо указать достаточно сведений для создания представления. Например для просмотра первого окна-разделителя, необходимо указать сведения класса представления и текущего документа.  
  
 Как правило, при использовании значения по умолчанию framework можно игнорировать `CCreateContext`. При попытке изменения более сложных, исходный код библиотеки Microsoft Foundation Class или примеров программ, таких как приложения, поможет. Если вы забыли обязательного параметра, утверждение framework сообщит, вы забыли.  
  
 Дополнительные сведения о `CCreateContext`, см. в образце MFC [приложения](../../visual-cpp-samples.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле afxext.h  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CFrameWnd::Create](../../mfc/reference/cframewnd-class.md#create)   
 [CFrameWnd::LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe)   
 [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)   
 [CSplitterWnd::Create](../../mfc/reference/csplitterwnd-class.md#create)   
 [CSplitterWnd::CreateView](../../mfc/reference/csplitterwnd-class.md#createview)   
 [CWnd::Create](../../mfc/reference/cwnd-class.md#create)


