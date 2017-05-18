---
title: "Класс CPtrList | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPtrList
dev_langs:
- C++
helpviewer_keywords:
- lists, generic
- CPtrList class
- generic lists
ms.assetid: 4139a09c-4338-4f42-9eea-51336120b43c
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 430d98d399e3c5131b248e10b9c7cfcec8dedc04
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cptrlist-class"></a>Класс CPtrList
Поддерживает списки пустых указателей.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CPtrList : public CObject  
```  
  
## <a name="members"></a>Члены  
 Функции-члены `CPtrList` похожи на функции-члены класса [CObList](../../mfc/reference/coblist-class.md). Из-за этой схожести для изучения этой функции-члена можно использовать справочную документацию по классу `CObList`. Если вы видите `CObject` указатель в качестве параметра функции или возвращаемого значения, заменить указатель `void`.  
  
 `CObject*& CObList::GetHead() const;`  
  
 , например, преобразуется в  
  
 `void*& CPtrList::GetHead() const;`  
  
## <a name="remarks"></a>Примечания  
 `CPtrList`включает в себя `IMPLEMENT_DYNAMIC` макрос для поддержки доступа типа во время выполнения и Сохранение дампа `CDumpContext` объекта. Если вам требуется дамп отдельных указатель список элементов, необходимо задать глубины контекста дампа 1 или выше.  
  
 Списки указатель не может быть сериализован.  
  
 Когда `CPtrList` удалить объект, или при удалении элементов, удаляются только указатели, не сущностями, которые они ссылаются.  
  
 Дополнительные сведения об использовании `CPtrList`, см. в статье [коллекции](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CPtrList`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcoll.h  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс cObList](../../mfc/reference/coblist-class.md)

