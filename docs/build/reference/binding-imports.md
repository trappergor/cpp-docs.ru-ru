---
title: Привязка Imports | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- /DELAY:NOBIND linker option
- DELAY:NOBIND linker option
ms.assetid: bb766038-deb1-41b1-bcbc-29a30e8c1e2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7519fb18ac7f24e79a5f7f664cb35f8eb5b3fd77
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="binding-imports"></a>Привязка Imports
По умолчанию компоновщик выполняется для создания связанной таблицы адресов импорта для библиотеки DLL, загружаемых с задержкой. Если библиотека DLL привязана, то вспомогательная функция будет пытаться использовать данные привязки вместо вызова метода **GetProcAddress** для каждого из импортов, на который указывает ссылка. Если отметка времени или предпочтительный адрес соответствуют таковым в загружаемой библиотеке DLL, вспомогательная функция будет предполагать, связанная таблица адресов импорта является устаревшим и будет продолжена, как если бы он не существует.  
  
 Если не требуется привязать импорты, загружаемые с задержкой DLL, указание [/delay](../../build/reference/delay-delay-load-import-settings.md): nobind в командной строке компоновщика препятствует связанная таблица адресов импорта генерировать и потреблять место в файле образа.  
  
## <a name="see-also"></a>См. также  
 [Поддержка компоновщика для библиотек DLL с отложенной загрузкой](../../build/reference/linker-support-for-delay-loaded-dlls.md)