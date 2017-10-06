---
title: "Соответствие C стандарту ANSI | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Ansi
dev_langs:
- C++
helpviewer_keywords:
- underscores, leading
- compatibility [C++], ANSI C
- compliance with ANSI C
- conventions [C++], Microsoft extensions
- underscores
- naming conventions [C++], Microsoft library
- ANSI [C++], C standard
- Microsoft extensions naming conventions
ms.assetid: 6be271bf-eecf-491a-a928-0ee2dd60e3b9
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 7e6c5d4045f0b71890a34d845b898844ca550ca8
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="ansi-c-compliance"></a>Совместимость ANSI с C
Соглашение об именовании для всех относящихся к системам Microsoft идентификаторов в системе времени выполнения (например, функций, макросов, констант, переменных и определений типов) соответствует стандарту ANSI. В этой документации любая функция времени выполнения, которая соответствует стандартам ANSI/ISO C, помечена как ANSI-совместимая. ANSI-совместимые приложения должны использовать только эти функции, соответствующие стандарту ANSI.  
  
 Имена функций и глобальных переменных, которые относятся к системам Microsoft, начинаются с одного символа подчеркивания. Эти имена можно переопределять только локально, в области действия своего кода. Например, при включении файлов заголовков времени выполнения Microsoft можно локально переопределить функцию для систем Microsoft с именем `_open`, объявив локальную переменную с таким же именем. Однако нельзя использовать это имя для собственных глобальных функций или глобальных переменных.  
  
 Имена относящихся к системам Microsoft макросов и констант манифеста начинаются с двух символов подчеркивания или с одного ведущего символа подчеркивания с идущей за ним прописной буквой. Область видимости этих идентификаторов абсолютна. Например, по этой причине вы не можете использовать идентификатор **_UPPER**, используемый исключительно в системах корпорации Майкрософт.  
  
## <a name="see-also"></a>См. также  
 [Совместимость](../c-runtime-library/compatibility.md)
