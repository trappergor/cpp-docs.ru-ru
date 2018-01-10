---
title: "Маршалинг | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f89b64794c50e381c07749984ce61579951fa02f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="marshaling"></a>маршалинг
Метод COM маршалинг позволяет интерфейсы, предоставляемые объектом в один процесс для использования в другом процессе. При маршалинге, предоставляет код COM (или использует код, предоставленный реализации интерфейса) для упаковки параметров метода в формат, который можно перемещать между процессами (а также, по каналу связи для процессов, выполняющихся на других компьютерах) и для распаковки этих параметров с другой стороны. Аналогично COM необходимо выполнить эти шаги при возврате из вызова.  
  
> [!NOTE]
>  Маршалинг обычно не является обязательным при использовании интерфейс, предоставляемый объект в том же процессе, что и объект. Тем не менее маршалинг будет требоваться между потоками.  
  
## <a name="see-also"></a>См. также  
 [Знакомство с COM](../atl/introduction-to-com.md)   
 [Сведения о маршалинге](http://msdn.microsoft.com/library/windows/desktop/ms692621)

