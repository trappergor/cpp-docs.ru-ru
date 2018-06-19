---
title: Предупреждение средств компоновщика LNK4037 | Документы Microsoft
ms.custom: ''
ms.date: 10/04/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4037
dev_langs:
- C++
helpviewer_keywords:
- LNK4037
ms.assetid: 9ba02fd3-b04f-4679-bab9-26fa82cf09bb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6b87f0a415d6ae7d282e29c2ca67fda043c2a901
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302439"
---
# <a name="linker-tools-warning-lnk4037"></a>Предупреждение средств компоновщика LNK4037

>"*символ*" не существует; пропускается

Внутреннее имя *символ* не могут быть упорядочены с помощью [/ORDER](../../build/reference/order-put-functions-in-order.md) , так как он не найден в программе. Проверьте спецификацию *символ* в файле ответов заказа. Дополнительные сведения см. в разделе [/Order (размещение функций по порядку)](../../build/reference/order-put-functions-in-order.md) компоновщика.

> [!NOTE]
> ССЫЛКА не может упорядочивать статические функции, поскольку имена не являются именами открытых символов. Когда **/ORDER** задается, данное предупреждение компоновщика создается для каждого символа в файле ответов заказа, является либо статическим или не найден.