---
title: Класс CPtrList
ms.date: 11/04/2016
f1_keywords:
- CPtrList
helpviewer_keywords:
- lists, generic
- CPtrList class [MFC]
- generic lists
ms.assetid: 4139a09c-4338-4f42-9eea-51336120b43c
ms.openlocfilehash: dfd545e1758ea257a89606655bf735829dbe8840
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50586398"
---
# <a name="cptrlist-class"></a>Класс CPtrList

Поддерживает списки пустых указателей.

## <a name="syntax"></a>Синтаксис

```
class CPtrList : public CObject
```

## <a name="members"></a>Участники

Функции-члены `CPtrList` похожи на функции-члены класса [CObList](../../mfc/reference/coblist-class.md). Из-за этой схожести для изучения этой функции-члена можно использовать справочную документацию по классу `CObList`. Если вы видите `CObject` указатель в качестве параметра функции или возвращаемого значения, заменить указатель на **void**.

`CObject*& CObList::GetHead() const;`

, например, преобразуется в

`void*& CPtrList::GetHead() const;`

## <a name="remarks"></a>Примечания

`CPtrList` включает в себя implement_dynamic-макрос для поддержки доступа типа времени выполнения и Сохранение дампа `CDumpContext` объекта. Если вам требуется дамп отдельных указатель на список элементов, необходимо задать глубины контекста дампа 1 или выше.

Списки указатель не может быть сериализован.

Когда `CPtrList` объект удаляется или когда его элементы удаляются, удаляются только указатели, не сущностями, которые они ссылаются.

Дополнительные сведения об использовании `CPtrList`, см. в статье [коллекций](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CPtrList`

## <a name="requirements"></a>Требования

**Заголовок:** afxcoll.h

## <a name="see-also"></a>См. также

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CObList](../../mfc/reference/coblist-class.md)
