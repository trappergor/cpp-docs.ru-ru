---
title: "Ошибка средств компоновщика LNK1000 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1000
dev_langs: C++
helpviewer_keywords: LNK1000
ms.assetid: 86421b9a-460a-4285-8dce-9b8257d78122
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e3733fb40165c07e9f8c28c723aa0c645740040f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1000"></a>Ошибка средств компоновщика LNK1000
Неизвестная ошибка; Обратитесь к документации по варианты технической поддержки  
  
 Соберите сведения об обстоятельствах возникновения ошибки, попытайтесь изолировать проблему и создать воспроизводимый тестовый случай, а затем обратитесь `Microsoft Product Support Services`. Сведения о том, как определить причину и отправить отчет об ошибках см. в разделе [http://support.microsoft.com/default.aspx?scid=kb;en-us;134650](http://support.microsoft.com/default.aspx?scid=kb;en-us;134650).  
  
 Данная ошибка может возникать, если смешать файлов стандартных заголовков (например, dos.h) и собственные файлы. `#include`стандартные заголовки во-первых, за которым следует файлов заголовка.