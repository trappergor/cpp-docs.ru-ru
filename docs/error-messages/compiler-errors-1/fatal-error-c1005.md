---
title: Неустранимая ошибка C1005
ms.date: 11/04/2016
f1_keywords:
- C1005
helpviewer_keywords:
- C1005
ms.assetid: 150daf8e-a38a-4669-9c1a-a05b5a1f65ef
ms.openlocfilehash: a84791367656729b1cbd50ca180368f6c01531a4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614465"
---
# <a name="fatal-error-c1005"></a>Неустранимая ошибка C1005

слишком большая строка для буфера

Строка в промежуточном файле компилятора вызвала переполнение буфера.

Эта ошибка может возникнуть, если размер параметра, передаваемого в параметр компилятора [/Fd](../../build/reference/fd-program-database-file-name.md) или [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) , превышает 256 байт.