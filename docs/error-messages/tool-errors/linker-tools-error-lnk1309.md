---
title: "Ошибка средств компоновщика LNK1309 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1309
dev_langs: C++
helpviewer_keywords: LNK1309
ms.assetid: 10146071-883f-4849-97d1-c7468f90efbb
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 425fb564ae2bd099746fc9b76b496595caa10a0b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1309"></a>Ошибка средств компоновщика LNK1309
модуль "type1" обнаружен; недопустима из-за /CLRIMAGETYPE:type2 коммутатора  
  
 Тип образа среды CLR была запрошена с **/CLRIMAGETYPE** , но компоновщик не удалось создать образ этого типа, так как один или несколько модулей несовместимы с этим типом.  
  
 Например, вы увидите LNK1309 при указании **/CLRIMAGETYPE:safe** и передать модуль, построенный с **/CLR: pure**.  
  
 LNK1309 также возникает при попытке выполнить построение приложения с частичным доверием CLR чисто с помощью ptrustu [d] .lib. Сведения о создании приложения с частичным доверием см. в разделе [как: создать частично доверенного приложения путем удаления зависимостей для библиотеки DLL CRT](../../dotnet/create-a-partially-trusted-application.md).  
  
 Дополнительные сведения см. в разделе [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) и [/CLRIMAGETYPE (указать Type of CLR Image)](../../build/reference/clrimagetype-specify-type-of-clr-image.md).