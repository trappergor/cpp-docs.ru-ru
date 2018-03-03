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
- CPtrList class [MFC]
- generic lists
ms.assetid: 4139a09c-4338-4f42-9eea-51336120b43c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d7e69c8c0d80fea2720ea436bf0bff796ae57a60
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cptrlist-class"></a>Класс CPtrList
Поддерживает списки пустых указателей.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CPtrList : public CObject  
```  
  
## <a name="members"></a>Участники  
 Функции-члены `CPtrList` похожи на функции-члены класса [CObList](../../mfc/reference/coblist-class.md). Из-за этой схожести для изучения этой функции-члена можно использовать справочную документацию по классу `CObList`. Если вы видите `CObject` указатель в качестве параметра функции или возвращаемого значения, заменить указатель `void`.  
  
 `CObject*& CObList::GetHead() const;`  
  
 , например, преобразуется в  
  
 `void*& CPtrList::GetHead() const;`  
  
## <a name="remarks"></a>Примечания  
 `CPtrList`включает в себя `IMPLEMENT_DYNAMIC` макрос для поддержки доступа типа во время выполнения и Сохранение дампа `CDumpContext` объекта. Если вам требуется дамп отдельных указатель список элементов, необходимо задать глубины контекста дампа 1 или выше.  
  
 Списки указатель не может быть сериализован.  
  
 Когда `CPtrList` объект удаляется или при его элементы будут удалены, удаляются только указатели, не сущностями, которые они ссылаются.  
  
 Дополнительные сведения об использовании `CPtrList`, см. в статье [коллекции](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CPtrList`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcoll.h  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CObList](../../mfc/reference/coblist-class.md)
