---
title: -KEYFILE (указать ключ или пару ключей для подписи сборки) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /keyfile
- VC.Project.VCLinkerTool.KeyFile
dev_langs:
- C++
helpviewer_keywords:
- /KEYFILE linker option
- -KEYFILE linker option
- KEYFILE linker option
ms.assetid: 9b71f8c0-541c-4fe5-a0c7-9364f42ecb06
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 476fd1e49a8c93363f00215d422a79eda808c321
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="keyfile-specify-key-or-key-pair-to-sign-an-assembly"></a>/KEYFILE (задание ключа или пары ключей для подписи сборки)
```  
/KEYFILE:filename  
```  
  
## <a name="remarks"></a>Примечания  
 Здесь:  
  
 *filename*  
 Файл, содержащий ключ. Заключать строку в двойные кавычки (» «), если он содержит пробелы.  
  
## <a name="remarks"></a>Примечания  
 Компоновщик вставляет открытый ключ в манифест сборки и затем подписывает окончательную сборку закрытым ключом. Чтобы создать файл ключа, введите [sn -k](/dotnet/framework/tools/sn-exe-strong-name-tool) *filename* из командной строки. Считается, что подписанная сборка имеет строгое имя.  
  
 Если компиляция выполняется с [/LN](../../build/reference/ln-create-msil-module.md), имя файла ключа сохраняется в модуле и включается в сборку, созданная при компиляции сборки, включающей явную ссылку на модуль через [#using](../../preprocessor/hash-using-directive-cpp.md), либо при компоновке с [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md).  
  
 Сведения о шифровании можно также передать в компоновщик с [/keycontainer](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md). Используйте [/delaysign](../../build/reference/delaysign-partially-sign-an-assembly.md) Если необходимо использовать частично подписанную сборку. В разделе [строгое имя сборки (подписывание сборки) (C + +/ CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) Дополнительные сведения о подписи сборки.  
  
 В случае оба **/keyfile** и **/keycontainer** указаны (в командной строке или с помощью настраиваемого атрибута), компоновщик сначала попытаются использовать контейнер ключей. В случае успеха сборка подписывается данными контейнера ключей. Если компоновщик контейнер ключей не обнаружен, будет предпринята файл, заданный параметром/keyfile. В случае успеха сборка подписывается данными из файла ключей, и эти данные о ключах будут помещены в контейнер ключей (аналогично команде sn -i); таким образом, при следующей компиляции контейнер ключей будет действителен.  
  
 Обратите внимание, что файл ключей может содержать только открытый ключ.  
  
 В разделе [Создание и использование сборок](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies) Дополнительные сведения о подписи сборки.  
  
 Доступны следующие параметры компоновщика, влияющие на создание сборки.  
  
-   [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Выберите страницу свойств **Командная строка** .  
  
4.  Введите параметр в **Дополнительные параметры** поле.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)