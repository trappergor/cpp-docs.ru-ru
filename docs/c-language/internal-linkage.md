---
title: Внутренняя компоновка | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- internal linkage
- linkage [C++], internal
ms.assetid: 80be7b51-c930-43db-94d6-4f09a64077bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 09b5a02b7892bff0233e37bbd63020a4d2904ec3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094212"
---
# <a name="internal-linkage"></a>Внутренняя компоновка

Если объявление идентификатора области видимости файла для объекта или функции содержит *описатель класса хранения* **static**, такой идентификатор использует внутреннюю компоновку. В противном случае идентификатор имеет внешнюю компоновку. Использование нетерминального параметра *storage-class-specifier* приводится в статье [Классы хранения](../c-language/c-storage-classes.md).

В пределах одной записи преобразования каждый экземпляр идентификатора с внутренней компоновкой обозначает тот же идентификатор или функцию. Идентификаторы с внутренней компоновкой уникальны для конкретной записи преобразования.

## <a name="see-also"></a>См. также

[Использование ключевого слова extern для задания компоновки](../cpp/using-extern-to-specify-linkage.md)