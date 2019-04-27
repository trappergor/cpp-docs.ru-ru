---
title: Предупреждение компилятора (уровень 1) C4276
ms.date: 11/04/2016
f1_keywords:
- C4276
helpviewer_keywords:
- C4276
ms.assetid: 9d738c2d-29e5-408a-b9ff-be1a850b2238
ms.openlocfilehash: 87f13f7da12a3f7e40aaad180e2a3bc83e121771
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207143"
---
# <a name="compiler-warning-level-1-c4276"></a>Предупреждение компилятора (уровень 1) C4276

«функция»: не предоставлен прототип; предполагается отсутствие параметров

При получении адреса функции с [__stdcall](../../cpp/stdcall.md) соглашение о вызовах, необходимо предоставить прототип, компилятор может создать декорированное имя функции. Так как *функция* не имеет прототипа, компилятор, создавая декорированное имя, предполагается, что функция не имеет параметров.