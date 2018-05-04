---
title: '@ (Указать файл ответа компилятора) | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '@'
dev_langs:
- C++
helpviewer_keywords:
- response files, C/C++ compiler
- '@ compiler option'
- cl.exe compiler, specifying response files
ms.assetid: 400fffee-909d-4f60-bf76-45833e822685
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f291ed9a0ccc86ea1ef6fe6703205d76cdcd0fa1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="-specify-a-compiler-response-file"></a>@ (указать файл ответа компилятора)
Указывает файл ответа компилятора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
@response_file  
```  
  
## <a name="arguments"></a>Аргументы  
 `response_file`  
 Текстовый файл, содержащий команды для компилятора.  
  
## <a name="remarks"></a>Примечания  
 Файл ответа может содержать любые команды, указанные в командной строке. Это может быть полезно в том случае, если аргументы командной строки превышает 127 символов.  
  
 Не удается указать **@** параметр в файле ответов. То есть файл ответа не удается внедрить другой файл ответа.  
  
 Из командной строки можно указать любое количество параметров файла ответа (например, `@respfile.1 @respfile.2`) как требуется.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
-   Файл ответа не может быть указана из среды разработки и должен быть указан в командной строке.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   Данного параметра компилятора программным способом нельзя.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)