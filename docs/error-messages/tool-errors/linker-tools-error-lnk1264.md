---
title: "Ошибка средств компоновщика LNK1264 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1264
dev_langs:
- C++
helpviewer_keywords:
- LNK1264
ms.assetid: 23b1aad7-d382-42c1-bae8-db68575c57a8
caps.latest.revision: 9
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 0d075c807a698e62b4d46fcbd39e660d3e39d469
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk1264"></a>Ошибка средств компоновщика LNK1264
указан параметр /LTCG:PGINSTRUMENT, но не требуется создание кода; инструментарий не сделан  
  
 **/ LTCG: PGINSTRUMENT** был указан, но OBJ-файлы, скомпилированные с [/GL](../../build/reference/gl-whole-program-optimization.md). И отказ канала не удается выполнить инструментирование. Должен существовать хотя бы один OBJ-файл в командной строке, компилируется с **/GL** , чтобы инструментирование могло произойти.  
  
 Профильная оптимизация (PGO) доступен только в 64-разрядного компилятора.
