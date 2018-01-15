---
title: "Структура CCreateContext | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: CCreateContext
dev_langs: C++
helpviewer_keywords: CCreateContext structure [MFC]
ms.assetid: 337a0e44-d910-49a8-afc0-c7207666a9dc
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 929ed0971f9b69bf8e98ae247957110e78ac33ba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ccreatecontext-structure"></a>Структура CCreateContext
Платформа использует `CCreateContext` структуры при создании окна фрейма и представления, связанные с документом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct CCreateContext  
```  
  
## <a name="remarks"></a>Примечания  
 `CCreateContext`Структура и не имеет базового класса.  
  
 При создании окна значения в этой структуре предоставляют сведения, используемые для соединения компонентов документа в представление данных. Необходимо использовать `CCreateContext` при переопределении части процесса создания.  
  
 Объект `CCreateContext` структура содержит указатели на документ, фрейм окна, представления и шаблон документа. Он также содержит указатель на `CRuntimeClass` , определяющий тип представления для создания. Информация о классе во время выполнения и указателя на текущий документ используются для динамического создания нового представления. В следующей таблице приведены, как и когда каждая `CCreateContext` член может быть использован:  
  
|Член|Тип|Что такое для|  
|------------|----------|--------------------|  
|`m_pNewViewClass`|`CRuntimeClass*`|`CRuntimeClass`для создания нового представления.|  
|`m_pCurrentDoc`|`CDocument*`|Существующий документ, который нужно связать с новым представлением.|  
|`m_pNewDocTemplate`|`CDocTemplate*`|Шаблон документа, связанных с созданием нового окна фрейма MDI.|  
|`m_pLastView`|`CView*`|Исходное представление, на котором моделируются дополнительные представления, как создание представления окна разделителя или создание во втором представлении, в документе.|  
|`m_pCurrentFrame`|`CFrameWnd*`|Окна фрейма, на котором моделируются дополнительных фреймов, как и создания второго окна фрейма в документе.|  
  
 Создавая шаблон документа документ и его связанные компоненты, она проверяет данные, хранящиеся в `CCreateContext` структуры. Например представление не следует создавать для несуществующего документа.  
  
> [!NOTE]
>  Все указатели в `CCreateContext` являются необязательными и могут быть `NULL` , если не задано или неизвестное.  
  
 `CCreateContext`используется функциями-членами, перечисленных в разделе «См.» Если планируется переопределить их, обратитесь к описания этих функций для получения конкретных сведений.  
  
 Вот несколько общих рекомендаций.  
  
-   При передаче в качестве аргумента для создания окна, как и в `CWnd::Create`, `CFrameWnd::Create`, и `CFrameWnd::LoadFrame`, создать контекст указывает, что новое окно должен быть подключен к. Для большинства окон всю структуру является необязательным и `NULL` указатель может быть передан.  
  
-   Для функций-членов переопределяемым таких как `CFrameWnd::OnCreateClient`, `CCreateContext` аргумент является необязательным.  
  
-   Для функций-членов участвующих в режиме создания, необходимо указать достаточно сведений для создания представления. Например для первое представление в окне разделителя, необходимо указать сведения о классе представления и текущего документа.  
  
 Как правило, при использовании значения по умолчанию framework, можно пропустить `CCreateContext`. При попытке изменения более сложные, исходный код библиотеки Microsoft Foundation Class или примеры программ, таких как приложения, поможет вам. Если вы забыли обязательным параметром, утверждение framework сообщит, вы забыли.  
  
 Дополнительные сведения о `CCreateContext`, см. в образце MFC [VIEWEX](../../visual-cpp-samples.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxext.h  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CFrameWnd::Create](../../mfc/reference/cframewnd-class.md#create)   
 [CFrameWnd::LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe)   
 [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)   
 [CSplitterWnd::Create](../../mfc/reference/csplitterwnd-class.md#create)   
 [CSplitterWnd::CreateView](../../mfc/reference/csplitterwnd-class.md#createview)   
 [CWnd::Create](../../mfc/reference/cwnd-class.md#create)

