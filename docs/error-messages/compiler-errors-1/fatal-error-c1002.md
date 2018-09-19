---
title: Неустранимая ошибка C1002 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1002
dev_langs:
- C++
helpviewer_keywords:
- C1002
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82f08255484b11f9f5d87fb67ac8ac7b401d4f6e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044149"
---
# <a name="fatal-error-c1002"></a>Неустранимая ошибка C1002

не хватает размера кучи на 2-ом проходе компилятора

Компилятор не хватило места динамической памяти во время второго прохода, возможно, из-за программа с слишком много символов или сложные выражения.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки

1. Разделите исходный файл на несколько небольших файлов.

1. Разделите выражения в виде небольших частей.

1. Удалите другие программы или драйверы, использующие память.