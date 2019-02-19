---
title: Внутренняя компоновка
ms.date: 11/04/2016
helpviewer_keywords:
- internal linkage
- linkage [C++], internal
ms.assetid: 80be7b51-c930-43db-94d6-4f09a64077bf
ms.openlocfilehash: 79601af27f847a3afe7e8bdaefa926cd45459847
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56150744"
---
# <a name="internal-linkage"></a>Внутренняя компоновка

Если объявление идентификатора области видимости файла для объекта или функции содержит *описатель класса хранения* **static**, такой идентификатор использует внутреннюю компоновку. В противном случае идентификатор имеет внешнюю компоновку. Использование нетерминального параметра *storage-class-specifier* приводится в статье [Классы хранения](../c-language/c-storage-classes.md).

В пределах одной записи преобразования каждый экземпляр идентификатора с внутренней компоновкой обозначает тот же идентификатор или функцию. Идентификаторы с внутренней компоновкой уникальны для конкретной записи преобразования.

## <a name="see-also"></a>См. также

[Использование ключевого слова extern для задания компоновки](../cpp/using-extern-to-specify-linkage.md)
