---
title: Предупреждение компилятора (уровень 1) C4276 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4276
dev_langs:
- C++
helpviewer_keywords:
- C4276
ms.assetid: 9d738c2d-29e5-408a-b9ff-be1a850b2238
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 40a6c85b460e9718a8816598afb016e9c7a493b9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116026"
---
# <a name="compiler-warning-level-1-c4276"></a>Предупреждение компилятора (уровень 1) C4276

«функция»: не предоставлен прототип; предполагается отсутствие параметров

При получении адреса функции с [__stdcall](../../cpp/stdcall.md) соглашение о вызовах, необходимо предоставить прототип, компилятор может создать декорированное имя функции. Так как *функция* не имеет прототипа, компилятор, создавая декорированное имя, предполагается, что функция не имеет параметров.