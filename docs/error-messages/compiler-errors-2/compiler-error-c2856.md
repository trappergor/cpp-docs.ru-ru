---
title: Ошибка компилятора C2856
ms.date: 11/04/2016
f1_keywords:
- C2856
helpviewer_keywords:
- C2856
ms.assetid: fe616c51-124e-49e3-9dd8-883ec1660680
ms.openlocfilehash: 1e515f250c8ab9d1008ded91b99176f1d86d7cd1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406851"
---
# <a name="compiler-error-c2856"></a>Ошибка компилятора C2856

\#Директива #pragma hdrstop не может быть в пределах блока #if

`hdrstop` Нельзя помещать в теле блока условной компиляции.

Переместить `#pragma hdrstop` инструкцию, чтобы область, которая не содержится в `#if/#endif` блока.