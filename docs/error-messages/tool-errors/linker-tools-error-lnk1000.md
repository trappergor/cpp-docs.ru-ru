---
title: Ошибка средств компоновщика LNK1000 | Документы Microsoft
ms.custom: ''
ms.date: 06/18/2018
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
ms.openlocfilehash: 7a01db36200995813ec4b6862e9ddd04c6f069ba
ms.sourcegitcommit: d06966efce25c0e66286c8047726ffe743ea6be0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2018
ms.locfileid: "36238686"
---
# <a name="linker-tools-error-lnk1000"></a>Ошибка средств компоновщика LNK1000

> Неизвестная ошибка; Обратитесь к документации по варианты технической поддержки

Соберите сведения об обстоятельствах возникновения ошибки, а затем попытайтесь изолировать проблему и создать воспроизводимый тестовый случай. Сведения о том, как определить причину и отправить отчет об ошибках см. в разделе [как сообщить о проблеме с помощью инструментов Visual C++ или документации](../../how-to-report-a-problem-with-the-visual-cpp-toolset.md).

Данная ошибка может возникать, если смешать файлов стандартных заголовков (например, Windows.h) и собственные файлы. Включите предкомпилированного заголовка, если любой, первым, а затем стандартные заголовки следуют файлов заголовка.