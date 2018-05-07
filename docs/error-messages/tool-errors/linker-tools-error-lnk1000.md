---
title: Ошибка средств компоновщика LNK1000 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1000
dev_langs:
- C++
helpviewer_keywords:
- LNK1000
ms.assetid: 86421b9a-460a-4285-8dce-9b8257d78122
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2f67df9c53b79fabfc9559380b5b57a72e64cb8a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1000"></a>Ошибка средств компоновщика LNK1000
Неизвестная ошибка; Обратитесь к документации по варианты технической поддержки  
  
 Соберите сведения об обстоятельствах возникновения ошибки, попытайтесь изолировать проблему и создать воспроизводимый тестовый случай, а затем обратитесь `Microsoft Product Support Services`. Сведения о том, как определить причину и отправить отчет об ошибках см. в разделе [ http://support.microsoft.com/default.aspx?scid=kb; en-us; 134650](http://support.microsoft.com/default.aspx?scid=kb;en-us;134650).  
  
 Данная ошибка может возникать, если смешать файлов стандартных заголовков (например, dos.h) и собственные файлы. `#include` стандартные заголовки во-первых, за которым следует файлов заголовка.