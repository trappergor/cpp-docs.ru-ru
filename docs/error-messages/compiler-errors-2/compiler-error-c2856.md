---
title: Ошибка компилятора C2856
ms.date: 11/04/2016
f1_keywords:
- C2856
helpviewer_keywords:
- C2856
ms.assetid: fe616c51-124e-49e3-9dd8-883ec1660680
ms.openlocfilehash: c88610607083ecfaf5f20cd585b479991fa51b44
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201903"
---
# <a name="compiler-error-c2856"></a>Ошибка компилятора C2856

\#директива pragma hdrstop не может находиться внутри блока #if

Директиву pragma `hdrstop` нельзя поместить в тело блока условной компиляции.

Переместите оператор `#pragma hdrstop` в область, которая не содержится в блоке `#if/#endif`.
