---
title: "Преобразование. Диагностика | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 3730ca7c-0147-452d-bd4a-6a1e97e9793e
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: bb7f826be88ebec640a6f3b40b38478eea91ed36
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="translation-diagnostics"></a>Трансляция. Диагностика
**ANSI 2.1.1.3** Определение диагностики  
  
 Microsoft C создает сообщения об ошибках в следующем виде:  
  
```  
  
filename( line-number ) : diagnostic Cnumbermessage  
```  
  
 где *filename* обозначает имя исходного файла, в котором была обнаружена ошибка; *line-number* — номер строки, в которой компилятор обнаружил ошибку; `diagnostic` имеет значение "error" (ошибка) или "warning" (предупреждение); `number` — уникальное четырехзначное число, определяющее ошибку или предупреждение (с предшествующим символом **C**, как указано в синтаксисе); а `message` — поясняющее сообщение.  
  
## <a name="see-also"></a>См. также  
 [Поведение, определяемое реализацией](../c-language/implementation-defined-behavior.md)
