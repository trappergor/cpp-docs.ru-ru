---
title: "Байтовые и широкие потоки | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Byte and Wide Streams
dev_langs:
- C++
helpviewer_keywords:
- byte streams
- wide streams
ms.assetid: 61ef0587-4cbc-4eb8-aae5-4c298dbbc6f9
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: c916caf1ee0b39567813921401ee02cbda83d222
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="byte-and-wide-streams"></a>Байты и широкие потоки
Байтовый поток обрабатывает файл как последовательность байтов. В рамках программы поток передает эту последовательность байтов в неизменном виде.  
  
 Широкий поток, в свою очередь, представляет файл как последовательность обобщенных символов в многобайтовой кодировке, для которых могут использоваться различные наборы правил кодирования. (Текстовые и двоичные файлы считываются и записываются так же, как было описано выше.) В рамках программы поток представляется как соответствующая последовательность расширенных символов. Преобразования между двумя представлениями выполняются в стандартной библиотеке C. У вас есть возможность изменять правила преобразования, вызывая функцию [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md), которая изменяет категорию `LC_CTYPE`. Правила преобразования для каждого широкого потока устанавливаются в тот момент, когда он становится многобайтовым, и эти правила сохранятся даже при последующем изменении категории `LC_CTYPE`.  
  
 Для широкого потока действуют те же ограничения позиционирования, что и для текстовых потоков. Более того, индикатор положения в файле часто должен учитывать кодировку, зависящую от состояния. Как правило, он содержит как байтовое смещение в пределах потока, так и объект типа `mbstate_t`. В таких условиях есть только один надежный способ получить позицию внутри файла для широкого потока (функция [fgetpos](../c-runtime-library/reference/fgetpos.md)) и только один надежный способ восстановить эту полученную позицию (функция [fsetpos](../c-runtime-library/reference/fsetpos.md)).  
  
## <a name="see-also"></a>См. также  
 [Файлы и потоки](../c-runtime-library/files-and-streams.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)
