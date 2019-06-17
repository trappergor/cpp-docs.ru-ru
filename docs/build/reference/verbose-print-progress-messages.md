---
title: /VERBOSE (печать сообщений о ходе выполнения)
ms.date: 06/13/2019
f1_keywords:
- /verbose
- VC.Project.VCLinkerTool.ShowProgress
helpviewer_keywords:
- -VERBOSE linker option
- linking [C++], session progress information
- Print Progress Messages linker option
- linker [C++], output dependency information
- /VERBOSE linker option
- dependencies [C++], dependency information in linker output
- VERBOSE linker option
ms.assetid: 9c347d98-4c37-4724-a39e-0983934693ab
ms.openlocfilehash: bbf7b5966c741535f26202979cbfd71f839cc537
ms.sourcegitcommit: e79188287189b76b34eb7e8fb1bfe646bdb586bc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2019
ms.locfileid: "67141667"
---
# <a name="verbose-print-progress-messages"></a>/VERBOSE (печать сообщений о ходе выполнения)

Выводит сообщения о ходе выполнения во время процесса компоновки.

## <a name="syntax"></a>Синтаксис

> **/VERBOSE**\[ **:** {**CLR**|**ICF**|**INCR**|**LIB**|**REF**|**SAFESEH**|**UNUSEDDELAYLOAD**|**UNUSEDLIBS**}\]

## <a name="remarks"></a>Примечания

Компоновщик отправляет сведения о ходе выполнения сеанса компоновки для **вывода** окна. В командной строке данные отправляются в стандартный вывод и могут быть перенаправлены в файл.

| Параметр | Описание |
| ------------ | ----------------- |
| /VERBOSE | Отображает подробные сведения о процессе компоновки. |
| / VERBOSE: СРЕДЫ CLR | Отображает сведения о действиях компоновщика, определенные для объектов и метаданных, скомпилированные с помощью [/CLR](clr-common-language-runtime-compilation.md). |
| /VERBOSE:ICF | Отображает сведения о действиях компоновщика, полученный в результате применения [/OPT: ICF](opt-optimizations.md). |
| /VERBOSE:INCR | Отображает сведения о процессе компоновки. |
| / VERBOSE: LIB | Отображает сообщения о ходе выполнения, указывающие только библиотеки, в котором выполняется поиск.<br/> Отображаемая информация включает процесс поиска библиотеки. Он перечисляет имена библиотек и объектов (с указанием полного пути), символ, разрешаемый из библиотеки и список объектов, которые ссылаются на этот символ. |
| / VERBOSE: REF | Отображает сведения о действиях компоновщика, полученный в результате применения [предотвратят](opt-optimizations.md). |
| /VERBOSE:SAFESEH | Отображает сведения о модулях, несовместимых с безопасной обработки при структурированных исключений [/SAFESEH](safeseh-image-has-safe-exception-handlers.md) не указан. |
| /VERBOSE:UNUSEDDELAYLOAD | Отображает сведения о задержках загрузки библиотек DLL, содержащих символы, не используется при создании образа. |
| /VERBOSE:UNUSEDLIBS | Отображает сведения обо всех файлах библиотеки, которые не используются при создании образа. |

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **командной строки** страницу свойств.

1. Добавить параметр, чтобы **Дополнительные параметры** поле.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ShowProgress%2A>.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
