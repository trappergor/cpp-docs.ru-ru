---
title: -SAFESEH (образ содержит безопасные обработчики исключений) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /SAFESEH
dev_langs:
- C++
helpviewer_keywords:
- /SAFESEH linker option
- -SAFESEH linker option
- SAFESEH linker option
ms.assetid: 7722ff99-b833-4c65-a855-aaca902ffcb7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 035485540135fb3b3b082de630b31d6bf934b3d9
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713886"
---
# <a name="safeseh-image-has-safe-exception-handlers"></a>Параметр /SAFESEH (образ содержит обработчики безопасных событий)

```
/SAFESEH[:NO]
```

Когда **/SAFESEH** указан, компоновщик только создаст образ, если он может также создать таблицу изображения безопасных обработчиков исключений. Эта таблица указывает, какие обработчики исключений являются допустимыми для образа операционной системы.

**/ SAFESEH** допустим только при связывании x86 целевых объектов. **/ SAFESEH** не поддерживается для платформ, которые уже имеют обработчики исключений. Например на x64 и ARM, все обработчики исключений, указаны в PDATA. ML64.exe поддерживает добавление аннотаций, сведения о SEH (XDATA и PDATA) в образ, позволяя помощью ml64 функции. См. в разделе [MASM для x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md) Дополнительные сведения.

Если **/SAFESEH** не указан, компоновщик создает образ с таблицей обработчиков безопасных исключений, если все модули совместимы с функцией безопасной обработки исключений. Если все модули, не совместимый с функцией безопасной обработки исключений, полученный в результате образ не будет содержать таблицу безопасных обработчиков исключений. Если [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) указывает WINDOWSCE или один из параметров EFI_ *, компоновщик не будет пытаться создавать образ с таблицей обработчиков безопасных исключений, так как ни один из этих подсистем можно использовать сведения.

Если **/SAFESEH:NO** указан, компоновщик не создаст образ с таблицей обработчиков безопасных исключений, даже если все модули совместимы с функцией безопасной обработки исключений.

Наиболее распространенными причинами компоновщик не сможет дать изображение обусловлено один или несколько входных файлов (модули) в компоновщик не совместима с компонентом обработчики безопасных исключений. Распространенной причиной для модуля не совместимы с безопасных обработчиков исключений является, так как он был создан с помощью компилятора из предыдущей версии Visual C++.

Можно также зарегистрировать функцию как структурированный обработчик исключений с помощью [. SAFESEH](../../assembler/masm/dot-safeseh.md).

Невозможно пометить существующий двоичном безопасных исключений обработчиков (или нет обработчиков исключений); сведения о безопасной обработки исключений должны добавляться во время сборки.

Возможность создать таблицу безопасных обработчиков исключений зависит от приложения, с помощью библиотеки времени выполнения C. При связывании с [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) и необходимо таблицу безопасных обработчиков исключений, необходимо предоставить структуру загрузки конфигурации (например, можно найти в исходном файле loadcfg.c библиотеки CRT), содержащий все записи, определенные для Visual C++. Пример:

```
#include <windows.h>
extern DWORD_PTR __security_cookie;  /* /GS security cookie */

/*
* The following two names are automatically created by the linker for any
* image that has the safe exception table present.
*/

extern PVOID __safe_se_handler_table[]; /* base of safe handler entry table */
extern BYTE  __safe_se_handler_count;  /* absolute symbol whose address is
                                           the count of table entries */
typedef struct {
    DWORD       Size;
    DWORD       TimeDateStamp;
    WORD        MajorVersion;
    WORD        MinorVersion;
    DWORD       GlobalFlagsClear;
    DWORD       GlobalFlagsSet;
    DWORD       CriticalSectionDefaultTimeout;
    DWORD       DeCommitFreeBlockThreshold;
    DWORD       DeCommitTotalFreeThreshold;
    DWORD       LockPrefixTable;            // VA
    DWORD       MaximumAllocationSize;
    DWORD       VirtualMemoryThreshold;
    DWORD       ProcessHeapFlags;
    DWORD       ProcessAffinityMask;
    WORD        CSDVersion;
    WORD        Reserved1;
    DWORD       EditList;                   // VA
    DWORD_PTR   *SecurityCookie;
    PVOID       *SEHandlerTable;
    DWORD       SEHandlerCount;
} IMAGE_LOAD_CONFIG_DIRECTORY32_2;

const IMAGE_LOAD_CONFIG_DIRECTORY32_2 _load_config_used = {
    sizeof(IMAGE_LOAD_CONFIG_DIRECTORY32_2),
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    &__security_cookie,
    __safe_se_handler_table,
    (DWORD)(DWORD_PTR) &__safe_se_handler_count
};
```

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Выберите **компоновщика** папки.

1. Выберите **командной строки** страницу свойств.

1. Введите параметр в **Дополнительные параметры** поле.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)