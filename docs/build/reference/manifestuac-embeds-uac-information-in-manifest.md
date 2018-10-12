---
title: -MANIFESTUAC (встраивает контроля учетных Записей в манифест сведений об) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.UACUIAccess
- VC.Project.VCLinkerTool.UACExecutionLevel
- VC.Project.VCLinkerTool.EnableUAC
dev_langs:
- C++
helpviewer_keywords:
- /MANIFESTUAC linker option
- MANIFESTUAC linker option
- -MANIFESTUAC linker option
ms.assetid: 2d243c39-fa13-493c-b56f-d0d972a1603a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d8c8c3cc219f0cf658dc2669ccc10adf3aba55bd
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49163534"
---
# <a name="manifestuac-embeds-uac-information-in-manifest"></a>/MANIFESTUAC (встраивает в манифест сведений об UAC)

Указывает, следует ли внедрять в манифест программы сведения о контроле учетных записей.

## <a name="syntax"></a>Синтаксис

```
/MANIFESTUAC
/MANIFESTUAC:NO
/MANIFESTUAC:fragment
/MANIFESTUAC:level=_level
/MANIFESTUAC:uiAccess=_uiAccess
```

### <a name="parameters"></a>Параметры

*Фрагмент*<br/>
Строка, содержащая `level` и `uiAccess` значения. Дополнительные сведения см. в разделе "Примечания" Далее в этом разделе.

*_уровень*<br/>
Один из *asInvoker*, *highestAvailable*, или *requireAdministrator*. По умолчанию asInvoker. Дополнительные сведения см. в разделе "Примечания" Далее в этом разделе.

*_uiAccess*<br/>
**значение true,** Если требуется приложению обходить уровни защиты пользовательского интерфейса и диска ввода к более высоким уровнем разрешений windows на рабочем столе, в противном случае — **false**. По умолчанию используется **false**. Значение **true** только для приложений со специальными возможностями интерфейса пользователя.

## <a name="remarks"></a>Примечания

Если указать несколько параметров/MANIFESTUAC, в командной строке, приоритет имеет последний из них.

Доступны следующие варианты для /MANIFESTUAC:level:

- `asInvoker`: Приложение будет выполняться с теми же разрешениями, что и запустивший его процесс. Приложения можно повысить уровень разрешений, выбрав **Запуск от имени администратора**.

- highestAvailable: приложение будет запущено с наивысшим уровнем разрешений, как. Если пользователь, запускающий процесс приложения является членом группы "Администраторы", этот параметр будет таким же, как requireAdministrator. Если самый высокий уровень доступа больше, чем уровень процесса открытия, система предложит ввести учетные данные.

- requireAdministrator: приложение будет выполняться с разрешениями администратора. Пользователь, запускающий процесс приложения должен быть членом группы "Администраторы". Если время открытия не запущена с правами администратора, система предложит ввести учетные данные.

С помощью параметра /MANIFESTUAC:fragment можно указать значения уровня и uiAccess за один шаг. Этот фрагмент должен быть в следующем формате:

```
"level=[ asInvoker | highestAvailable | requireAdministrator ] uiAccess=[ true | false ]"
```

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Разверните узел **Свойства конфигурации**.

1. Разверните **компоновщика** узла.

1. Выберите **файл манифеста** страницу свойств.

1. Изменить **включить пользователя учетной записи (UAC)**, **уровень выполнения UAC**, и **обход защиты пользовательского интерфейса UAC** свойства.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableUAC%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACExecutionLevel%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACUIAccess%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)