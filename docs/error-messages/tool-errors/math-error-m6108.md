---
title: Математическая ошибка M6108 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6108
dev_langs:
- C++
helpviewer_keywords:
- M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1624a89b472733b4adb5563c8ba52e0b03dcaa2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048621"
---
# <a name="math-error-m6108"></a>Математическая ошибка M6108

квадратный корень

Операнд в операции квадратный корень было отрицательным.

Программа завершается с кодом выхода 136.

> [!NOTE]
>  `sqrt` Функции в библиотеке времени выполнения C и встроенная функция FORTRAN **SQRT** не создают эту ошибку. C `sqrt` функция проверяет аргумент перед выполнением операции и возвращает значение ошибки, если операнд является отрицательным. FORTRAN **SQRT** функция создает ошибку домена [M6201](../../error-messages/tool-errors/math-error-m6201.md) вместо этой ошибки.