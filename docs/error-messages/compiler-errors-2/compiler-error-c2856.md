---
title: Ошибка компилятора C2856 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2856
dev_langs:
- C++
helpviewer_keywords:
- C2856
ms.assetid: fe616c51-124e-49e3-9dd8-883ec1660680
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: df6226bfd2fc11f05f894091f4ff02c145d09e11
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072723"
---
# <a name="compiler-error-c2856"></a>Ошибка компилятора C2856

\#Директива #pragma hdrstop не может быть в пределах блока #if

`hdrstop` Нельзя помещать в теле блока условной компиляции.

Переместить `#pragma hdrstop` инструкцию, чтобы область, которая не содержится в `#if/#endif` блока.