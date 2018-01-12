---
title: "-SAFESEH (образ содержит обработчики безопасных событий) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /SAFESEH
dev_langs: C++
helpviewer_keywords:
- /SAFESEH linker option
- -SAFESEH linker option
- SAFESEH linker option
ms.assetid: 7722ff99-b833-4c65-a855-aaca902ffcb7
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1c57a882e3a421d03b2edf97c9fb4bf2f352e5d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="safeseh-image-has-safe-exception-handlers"></a>Параметр /SAFESEH (образ содержит обработчики безопасных событий)
```  
/SAFESEH[:NO]  
```  
  
 Когда **/SAFESEH** указан, компоновщик только создает образ, он может также создать таблицу изображения безопасных обработчиков исключений. В этой таблице указано, какие обработчики исключений являются допустимыми для образа операционной системы.  
  
 **/ Параметр SAFESEH** допустим только при компоновке x86 целевых объектов. **/ Параметр SAFESEH** не поддерживается для платформы, на которых уже есть обработчики исключений. Например, на [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] и ARM, все исключения, обработчиками, указаны в PDATA. ML64.exe реализована поддержка Добавление заметок, которые выдают сведения SEH (XDATA и PDATA) в образ, позволяя очистки через ml64 функции. В разделе [MASM для x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md) для получения дополнительной информации.  
  
 Если **/SAFESEH** не указан, компоновщик создает образ с таблицей обработчиков безопасных исключений, если все модули совместимы с функцией обработки безопасных исключений. Если каких-либо модулей, не совместимый с функцией безопасной обработки исключений, полученный в результате образ не будет содержать таблицу безопасных обработчиков исключений. Если [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) указывает WINDOWSCE или один из параметров EFI_ *, компоновщик не будет пытаться создать образ с таблицей обработчиков безопасных исключений как ни один из этих подсистем можно использовать сведения.  
  
 Если **/SAFESEH:NO** указан, компоновщик не создает образ с таблицей обработчиков безопасных исключений, даже если все модули совместимы с функцией безопасной обработки исключений.  
  
 Наиболее частая причина компоновщик не сможет дать изображение — так как один или несколько входных файлов компоновщика (модули) несовместим с компонентом обработчики безопасных исключений. Обычная причина для модуля не совместимы с безопасных обработчиков исключений — так как он был создан с помощью компилятора предыдущей версии Visual C++.  
  
 Также можно зарегистрировать функцию в качестве обработчика структурированных исключений с помощью [. SAFESEH](../../assembler/masm/dot-safeseh.md).  
  
 Невозможно пометить существующий двоичном безопасных исключений обработчики (или нет обработчиков исключений); сведения об обработке безопасных исключений должны добавляться во время построения.  
  
 Компоновщик возможность создавать таблицу безопасных обработчиков исключений зависит от приложения, с помощью библиотеки времени выполнения C. При связывании с [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) и необходимо таблицу безопасных обработчиков исключений, необходимо предоставить структуру загрузки конфигурации (например, можно найти в исходном файле loadcfg.c библиотеки CRT), содержащий все элементы, определенные для Visual C++. Пример:  
  
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
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Выберите **компоновщика** папки.  
  
3.  Выберите **командной строки** страницу свойств.  
  
4.  Введите параметр в **Дополнительные параметры** поле.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)