---
title: Маршалинг | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d2b8b82d5369aa536dab638efa379089325d10b1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="marshaling"></a>маршалинг
Метод COM маршалинг позволяет интерфейсы, предоставляемые объектом в один процесс для использования в другом процессе. При маршалинге, предоставляет код COM (или использует код, предоставленный реализации интерфейса) для упаковки параметров метода в формат, который можно перемещать между процессами (а также, по каналу связи для процессов, выполняющихся на других компьютерах) и для распаковки этих параметров с другой стороны. Аналогично COM необходимо выполнить эти шаги при возврате из вызова.  
  
> [!NOTE]
>  Маршалинг обычно не является обязательным при использовании интерфейс, предоставляемый объект в том же процессе, что и объект. Тем не менее маршалинг будет требоваться между потоками.  
  
## <a name="see-also"></a>См. также  
 [Знакомство с COM](../atl/introduction-to-com.md)   
 [Сведения о маршалинге](http://msdn.microsoft.com/library/windows/desktop/ms692621)

