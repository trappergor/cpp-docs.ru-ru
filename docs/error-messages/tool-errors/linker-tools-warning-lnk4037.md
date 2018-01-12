---
title: "Предупреждение средств компоновщика LNK4037 | Документы Microsoft"
ms.custom: 
ms.date: 10/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4037
dev_langs: C++
helpviewer_keywords: LNK4037
ms.assetid: 9ba02fd3-b04f-4679-bab9-26fa82cf09bb
caps.latest.revision: "0"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0c93eab2faf81e4cd743eae4befa2f842c100589
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4037"></a>Предупреждение средств компоновщика LNK4037

>"*символ*" не существует; пропускается

Внутреннее имя *символ* не могут быть упорядочены с помощью [/ORDER](../../build/reference/order-put-functions-in-order.md) , так как он не найден в программе. Проверьте спецификацию *символ* в файле ответов заказа. Дополнительные сведения см. в разделе [/Order (размещение функций по порядку)](../../build/reference/order-put-functions-in-order.md) компоновщика.

> [!NOTE]
> ССЫЛКА не может упорядочивать статические функции, поскольку имена не являются именами открытых символов. Когда **/ORDER** задается, данное предупреждение компоновщика создается для каждого символа в файле ответов заказа, является либо статическим или не найден.