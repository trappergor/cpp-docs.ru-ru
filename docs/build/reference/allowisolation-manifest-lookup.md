---
title: -ALLOWISOLATION (поиск манифеста) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /ALLOWISOLATION
- VC.Project.VCLinkerTool.AllowIsolation
dev_langs:
- C++
helpviewer_keywords:
- -ALLOWISOLATION linker option
- /ALLOWISOLATION linker option
ms.assetid: 6d41851e-b3c1-4bdf-beaa-031773089d6f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a0e063aa51e136dfcc7a4445948e8a68d7a99bca
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369842"
---
# <a name="allowisolation-manifest-lookup"></a>/ALLOWISOLATION (поиск манифеста)
Задает поведение нахождения файлов манифеста.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/ALLOWISOLATION[:NO]  
```  
  
## <a name="remarks"></a>Примечания  
 **/ALLOWISOLATION:no** указывает библиотеки DLL загружаются, как если бы манифеста не было в результате чего компоновщику задание `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` бит в необязательном заголовке `DllCharacteristics` поля.  
  
 **/ ALLOWISOLATION** вынуждает операционную систему на поиск и загрузку манифеста.  
  
 **/ ALLOWISOLATION** значение по умолчанию.  
  
 При отключении изоляции для исполняемого файла загрузчик Windows не будет пытаться обнаружить манифест приложения для нового процесса. Новый процесс не будет контекста активации по умолчанию, даже если отсутствует манифест в исполняемый файл или размещено в том же каталоге, что и исполняемый файл с именем * исполняемый-name ***. exe.manifest**.  
  
 Дополнительные сведения см. в разделе [файлы манифеста ссылаются](http://msdn.microsoft.com/library/aa375632).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Разверните **свойства конфигурации** узла.  
  
3.  Разверните **компоновщика** узла.  
  
4.  Выберите **файл манифеста** страницу свойств.  
  
5.  Изменить **Разрешить изоляцию** свойство.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)