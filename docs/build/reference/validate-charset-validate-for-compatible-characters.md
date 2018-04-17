---
title: -проверки-charset (проверки для совместимых символов) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- /validate-charset
- validate-charset
dev_langs:
- C++
helpviewer_keywords:
- /validate-charset compiler option
ms.assetid: 50360fd0-4d32-4a4f-95d0-53d38c12ad4c
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0e82b9fd42b636cffd318f6327cc064687334329
ms.sourcegitcommit: 770f6c4a57200aaa9e8ac6e08a3631a4b4bdca05
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="validate-charset-validate-for-compatible-characters"></a>/ Validate-CharSet (проверки для совместимых символов)
Проверяет, что исходного текста файла содержит только символов может быть представлен как UTF-8.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/validate-charset[-]  
```  
  
## <a name="remarks"></a>Примечания  
 Можно использовать **/Validate-CharSet** параметр, чтобы проверить, что исходный код содержит только набор символов, которые могут быть представлены в исходной кодировки и кодировки выполнения. Эта проверка включается автоматически при указании **/Source-CharSet**, **/Execution-CharSet**, или **/UTF-8** параметры компилятора. Можно явно отключить эту проверку, указав **/ validate-charset -** параметр.  
  
 По умолчанию Visual Studio определяет метку порядка байтов, чтобы определить, если исходный файл в кодировке Юникод, например, UTF-16 или UTF-8. Если найдена метка порядка байтов отсутствуют, предполагается исходный файл кодируются с помощью текущей кодовой странице пользователя, пока не задана кодовая страница с помощью **/UTF-8** или **/Source-CharSet** параметр. Visual Studio позволяет сохранить исходный код C++ с помощью любого из нескольких кодировки символов. Сведения об исходной и кодировка выполнения см. в разделе [кодировки](../../cpp/character-sets.md) в документацию по языку. Список поддерживаемых идентификаторы кодовой страницы и кодировку имен, см. в разделе [идентификаторы кодовой страницы](http://msdn.microsoft.com/library/windows/desktop/dd317756).  
  
 Visual Studio использует UTF-8 для кодирования внутренних символов при преобразовании между исходная кодировка и кодировка выполнения. Если символ в исходном файле, невозможно представить в кодировке выполнения, преобразования UTF-8 подставляет вопросительный знак "?" символов. **/Validate-CharSet** вынуждает компиляции выдать предупреждение, если это происходит.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Разверните **свойства конфигурации**, **C/C++**, **командной строки** папки.  
  
3.  В **Дополнительные параметры**, добавьте **/Validate-CharSet** и задайте предпочтительной кодировки.  
  
4.  Выберите **ОК** для сохранения изменений.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)   
 [/ Execution-CharSet (задать выполнение кодировки)](../../build/reference/execution-charset-set-execution-character-set.md)   
 [/ Source-CharSet (задать исходной кодировки)](../../build/reference/source-charset-set-source-character-set.md)   
 [/utf/8 (указание UTF/8 в качестве исходной кодировки и кодировки исполняемого файла)](../../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)