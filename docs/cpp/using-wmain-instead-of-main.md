---
title: "Использование wmain вместо main | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- wmain
dev_langs:
- C++
helpviewer_keywords:
- main function, vs. wmain
- wmain function
ms.assetid: 7abb1257-b85c-413a-b913-d45b1582a71d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d43ab12c42315d735220af8f91c40d8b6a5cc4f9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="using-wmain-instead-of-main"></a>Использование wmain вместо main
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 В модели программирования Юникода можно определить версию функции **main** для расширенных символов. Используйте **wmain** вместо **основной** Если требуется создать переносимый код, который соответствует спецификации Юникода.  
  
 Формальные параметры для функции **wmain** объявляются в том же формате, что и для функции **main**. Затем можно передать в качестве аргументов "широкие" символы и указатель среды кодировки Юникод (необязательно) в программу. Параметры `argv` и `envp` для функции **wmain** относятся к типу `wchar_t*`.  
  
 Если программа использует **основной** функция, среда многобайтовой кодировки создается операционной системой при запуске программы. Двухбайтовые копия среды создается только при необходимости (например, с помощью вызова [_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md) или [_wputenv](../c-runtime-library/reference/putenv-wputenv.md) функции). При первом вызове `_wputenv` или `_wgetenv`, если среда многобайтовой кодировки (MBCS) уже существует, создается соответствующая среда широкосимвольной строки, на которую затем указывает глобальная переменная `_wenviron`, представляющая собой широкосимвольную версию глобальной переменной `_environ`. В этот момент две копии среды (для многобайтовой кодировки и Юникода) существуют одновременно и поддерживаются операционной системой в течение всего срока жизни программы.  
  
 Аналогично Если программа использует **wmain** функция, среда многобайтовой Кодировки (ASCII) создается при первом вызове для `_putenv` или `getenv`и на нее указывает `_environ` глобальной переменной.  
  
 Дополнительные сведения о среде MBCS см. в разделе [однобайтовые и многобайтовые кодировки](../c-runtime-library/single-byte-and-multibyte-character-sets.md) в *Справочник по библиотеке времени выполнения.*  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Функция main: запуск программы](../cpp/main-program-startup.md)