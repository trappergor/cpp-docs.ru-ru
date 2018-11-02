---
title: Ошибка компилятора C2856
ms.date: 11/04/2016
f1_keywords:
- C2856
helpviewer_keywords:
- C2856
ms.assetid: fe616c51-124e-49e3-9dd8-883ec1660680
ms.openlocfilehash: 1e515f250c8ab9d1008ded91b99176f1d86d7cd1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499610"
---
# <a name="compiler-error-c2856"></a>Ошибка компилятора C2856

\#Директива #pragma hdrstop не может быть в пределах блока #if

`hdrstop` Нельзя помещать в теле блока условной компиляции.

Переместить `#pragma hdrstop` инструкцию, чтобы область, которая не содержится в `#if/#endif` блока.