---
title: Неустранимая ошибка компилятора ресурсов RC1120 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC1120
dev_langs:
- C++
helpviewer_keywords:
- RC1120
ms.assetid: 4e462931-e42e-42e3-8bfc-847677194286
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62f28e381d4eac0bfd1f010ef3919452635a1b96
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057006"
---
# <a name="resource-compiler-fatal-error-rc1120"></a>Неустранимая ошибка компилятора ресурсов RC1120

не хватает памяти необходимо количество байтов

Компилятору ресурсов не хватило места для хранения элементов, хранимых в его кучи. Обычно это результат использования слишком много символов.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки

1. Увеличьте размер файла подкачки Windows. Дополнительные сведения об увеличении размер файла подкачки см. в разделе виртуальной памяти в справке Windows.

1. Удалите неиспользуемые включаемых файлов, особенно ненужные `#define`и прототипы функций.

1. Разделите данный файл в два или более файлов и компилировать их отдельно.

1. Удалите другие программы или драйверы, запущенные в системе, которая может расходоваться значительный объем памяти.