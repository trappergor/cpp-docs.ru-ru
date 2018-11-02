---
title: Предупреждение средств компоновщика LNK4037
ms.date: 10/04/2017
f1_keywords:
- LNK4037
helpviewer_keywords:
- LNK4037
ms.assetid: 9ba02fd3-b04f-4679-bab9-26fa82cf09bb
ms.openlocfilehash: 9a8121617e622fc12efe5bd26aac23faf2530f24
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607406"
---
# <a name="linker-tools-warning-lnk4037"></a>Предупреждение средств компоновщика LNK4037

>"*символ*" не существует; пропускается

Внутреннее имя *символ* не может быть упорядочены с помощью [/ORDER](../../build/reference/order-put-functions-in-order.md) параметр, так как он не найден в программе. Проверьте спецификацию *символ* в файле ответов заказа. Дополнительные сведения см. в разделе [/Order (размещение функций по порядку)](../../build/reference/order-put-functions-in-order.md) параметр компоновщика.

> [!NOTE]
> ССЫЛКА не может упорядочивать статические функции, поскольку имена не являются именами открытых символов. Когда **/ORDER** задается, данное предупреждение компоновщика создается для каждого символа в файле ответов порядок, в которые статичны или не найден.