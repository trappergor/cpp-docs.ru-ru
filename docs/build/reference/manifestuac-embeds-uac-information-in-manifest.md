---
title: /MANIFESTUAC (встраивает в манифест сведений об UAC)
ms.date: 06/12/2020
f1_keywords:
- VC.Project.VCLinkerTool.UACUIAccess
- VC.Project.VCLinkerTool.UACExecutionLevel
- VC.Project.VCLinkerTool.EnableUAC
helpviewer_keywords:
- /MANIFESTUAC linker option
- MANIFESTUAC linker option
- -MANIFESTUAC linker option
ms.assetid: 2d243c39-fa13-493c-b56f-d0d972a1603a
ms.openlocfilehash: 96719c6f6f5359afb03b967524b1f65db6dc664a
ms.sourcegitcommit: 8645408c7929558b8162f781776d0908d790a41c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85334940"
---
# <a name="manifestuac-embeds-uac-information-in-manifest"></a>/MANIFESTUAC (встраивает в манифест сведений об UAC)

Указывает, следует ли внедрять в манифест программы сведения о контроле учетных записей.

## <a name="syntax"></a>Синтаксис

> **`/MANIFESTUAC`**\
> **`/MANIFESTUAC:NO`**\
> **`/MANIFESTUAC:`**_`level`_\
> **`/MANIFESTUAC:`**_`uiAccess`_\
> **`/MANIFESTUAC:`**_`fragment`_

### <a name="parameters"></a>Параметры

**`NO`**<br/>
Компоновщик не внедряет сведения о контроле учетных записей в манифест программы.

*`level`*<br/>
**`level=`**, за которым следует один из **`'asInvoker'`** , **`'highestAvailable'`** или **`'requireAdministrator'`** . По умолчанию имеет значение **`'asInvoker'`** . Дополнительные сведения см. в разделе [Примечания](#remarks).

*`uiAccess`*<br/>
**`uiAccess='true'`** Если требуется, чтобы приложение обходило уровни защиты пользовательского интерфейса и входные данные в окнах с более высоким разрешением на рабочем столе; в противном случае — **`uiAccess='false'`** . По умолчанию имеет значение **`uiAccess='false'`** . Задайте для этого аргумента значение **`uiAccess='true'`** только для приложений со специальными возможностями пользовательского интерфейса.

*`fragment`*<br/>
Строка, содержащая *`level`* *`uiAccess`* значения и. При необходимости можно заключить в двойные кавычки. Дополнительные сведения см. в разделе [Примечания](#remarks).

## <a name="remarks"></a>Комментарии

Если **`/MANIFESTUAC`** в командной строке задано несколько параметров, приоритет имеет последний из введенных значений.

Возможны **`/MANIFESTUAC:`** _`level`_ следующие варианты:

- **`level='asInvoker'`**: Приложение выполняется на том же уровне разрешений, что и процесс, который его запустил. Вы можете повысить уровень разрешений приложения, выбрав **Запуск от имени администратора**.

- **`level='highestAvailable'`**: Приложение работает с наивысшим уровнем разрешений, который он может иметь. Если пользователь, запускающий приложение, является членом группы "Администраторы", этот параметр имеет то же значение, что и **`level='requireAdministrator'`** . Если максимальный доступный уровень разрешений выше уровня процесса открытия, система запрашивает учетные данные.

- **`level='requireAdministrator'`**: Приложение запускается с правами администратора. Пользователь, запускающий приложение, должен быть членом группы "Администраторы". Если открывающий процесс не выполняется с правами администратора, система запрашивает учетные данные.

Можно указать оба *`level`* *`uiAccess`* значения и в одном шаге с помощью **`/MANIFESTUAC:`** _`fragment`_ параметра. Фрагмент должен иметь следующий вид:

> **`/MANIFESTUAC:`** \[ **`"`** ] **`level=`** { **`'asInvoker'`** | **`'highestAvailable'`** | **`'requireAdministrator'`** } **`uiAccess=`** { **`'true'`** | **`'false'`** } \[ **`"`** ]

Пример.

**`/MANIFESTUAC:"level='highestAvailable' uiAccess='true'"`**

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Откройте **Configuration Properties**  >  **Linker**  >  страницу свойств**файл манифеста** компоновщика свойств конфигурации.

1. Измените параметры **включить контроль учетных записей пользователей (UAC)**, **уровень выполнения UAC**и **Обход свойств защиты пользовательского интерфейса UAC** .

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableUAC%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACExecutionLevel%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACUIAccess%2A>.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
