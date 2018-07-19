---
title: -ИГНОРИРОВАТЬ (пропускать определенные предупреждения) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /OVERWRITE
dev_langs:
- C++
helpviewer_keywords:
- /IGNORE linker option
ms.assetid: 37e77387-8838-4697-898f-d376ac641124
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b096fc12f69fbe637a3067646c20f6d520a9250f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378013"
---
# <a name="ignore-ignore-specific-warnings"></a>/IGNORE (пропускать определенные предупреждения)
```  
/IGNORE:warning[,warning]  
```  
  
## <a name="parameters"></a>Параметры  
 `warning`  
 Количество подавляемых предупреждений компоновщика в диапазоне от 4000 до 4999.  
  
## <a name="remarks"></a>Примечания  
 По умолчанию LINK выводит все предупреждения. Укажите **/IGNORE:** `warning` сообщить компоновщик подавлял предупреждения с определенным номером. Чтобы подавить предупреждения нескольких типов, укажите их номера через запятую.  
  
 Компоновщик не допускает подавление некоторых предупреждений. В этой таблице перечислены предупреждения, которые не подавляются в **/IGNORE**:  
  
|Предупреждение компоновщика||  
|--------------------|-|  
|LNK4017|оператор `keyword` не поддерживается для платформы назначения; пропускается|  
|[LNK4044](../../error-messages/tool-errors/linker-tools-warning-lnk4044.md)|параметр '`option`' не распознан; пропускается|  
|LNK4062|"`option`«не совместим с»`architecture`" целевой компьютер; параметр пропускается|  
|[LNK4075](../../error-messages/tool-errors/linker-tools-warning-lnk4075.md)|пропуск "`option1`", поскольку указано "`option2`"|  
|[LNK4086](../../error-messages/tool-errors/linker-tools-warning-lnk4086.md)|точка входа '`function`' не является __stdcall с '`number`' байт аргументов; образ может не работать|  
|LNK4088|образ создается, поскольку указан параметр /FORCE; образ может не работать|  
|[LNK4105](../../error-messages/tool-errors/linker-tools-warning-lnk4105.md)|не указан аргумент параметра '`option`'; параметр пропускается|  
|LNK4203|ошибка при чтении базы данных программы '`filename`'; компоновка объекта без отладочной информации|  
|[LNK4204](../../error-messages/tool-errors/linker-tools-warning-lnk4204.md)|"`filename`" отсутствуют отладочные данные для ссылок на модуль; компоновка объекта выполняется как при отсутствии отладочных данных|  
|[LNK4205](../../error-messages/tool-errors/linker-tools-warning-lnk4205.md)|"`filename`" отсутствует текущие отладочные данные для ссылок на модуль; компоновка объекта выполняется как при отсутствии отладочных данных|  
|[LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md)|заранее скомпилированная информация о типе не найдена; '`filename`' не скомпонован или перезаписан; компоновка объекта без отладочной информации|  
|LNK4207|"`filename`" откомпилирован /Yc /Yu/Z7; не удается создать PDB; перекомпилируйте с /Zi; компоновка объекта выполняется как при отсутствии отладочных данных|  
|LNK4208|несовместимый формат PDB в '`filename`'; удалите и заново соберите; компоновка объекта без отладочной информации|  
|LNK4209|повреждена отладочная информация; заново скомпилируйте модуль; компоновка объекта без отладочной информации|  
|[LNK4224](../../error-messages/tool-errors/linker-tools-warning-lnk4224.md)|`option` больше не поддерживается; пропускается|  
|LNK4228|"`option`" недопустимо для библиотеки DLL; пропускается|  
|[LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)|обнаружена недопустимая директива /`directive`; пропускается|  
  
 Как правило, предупреждения компоновщика, которые нельзя отключить, указывают на сбои сборки, ошибки в командной строке или ошибки конфигурации, которые следует исправить.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  В **компоновщика** выберите **командной строки** страницу свойств.  
  
3.  Изменить **Дополнительные параметры** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.