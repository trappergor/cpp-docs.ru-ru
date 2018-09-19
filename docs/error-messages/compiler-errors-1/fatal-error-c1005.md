---
title: Неустранимая ошибка C1005 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1005
dev_langs:
- C++
helpviewer_keywords:
- C1005
ms.assetid: 150daf8e-a38a-4669-9c1a-a05b5a1f65ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 888bdaf2eaddc0d4178affa1ccc4ae77c34f4617
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46092314"
---
# <a name="fatal-error-c1005"></a>Неустранимая ошибка C1005

слишком большая строка для буфера

Строка в промежуточном файле компилятора вызвала переполнение буфера.

Эта ошибка может возникнуть, если размер параметра, передаваемого в параметр компилятора [/Fd](../../build/reference/fd-program-database-file-name.md) или [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) , превышает 256 байт.