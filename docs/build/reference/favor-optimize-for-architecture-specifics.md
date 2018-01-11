---
title: "-favor (оптимизация для особенностей архитектуры) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /favor
dev_langs: C++
helpviewer_keywords:
- -favor compiler option [C++]
- /favor compiler option [C++]
ms.assetid: ad264df2-e30f-4d68-8bd0-10d6bee71a2a
caps.latest.revision: "31"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4f9ec5882cb1535f089250bc467c795263132d35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="favor-optimize-for-architecture-specifics"></a>/favor (оптимизация для особенностей архитектуры)
**/ favor:** `option` создает код, оптимизированный для конкретной архитектуры или для специфики микроархитектур в архитектурах Intel и AMD.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/favor:{blend | ATOM | AMD64 | INTEL64}  
```  
  
## <a name="remarks"></a>Примечания  
 **/favor:Blend**  
 (x86- и x64) создает код, который оптимизирован для специфики микроархитектур в архитектурах Intel и AMD. Хотя **/favor:blend** может не обеспечивать максимальную производительность невозможно для конкретного процессора, предназначенный для обеспечения оптимальной производительности для широкого x86- и x64 процессоров. По умолчанию **/favor:blend** действует.  
  
 **/favor:Atom**  
 (x86- и x64) создает код, который оптимизирован для специфики процессором Intel Atom и технологии Intel Centrino Atom. Код, созданный с помощью **/favor:ATOM** может привести к инструкции Intel SSSE3, SSE3, SSE и SSE2 для процессоров Intel.  
  
 **/favor:AMD64**  
 (x64) оптимизирует созданный код для AMD Opteron и Athlon, поддерживающих 64-разрядных расширений. Оптимизированный код может выполняться на всех x64 совместимые платформы. Код, созданный с помощью **/favor:AMD64** может привести к снижению производительности для процессоров Intel®, поддерживающих технологию Intel64.  
  
 **/favor:Intel64**  
 (x64) оптимизирует созданный код для процессоров Intel®, поддерживающих технологию Intel64, который обычно обеспечивает более высокую производительность для данной платформы. Результирующий код может работать на любой x64 платформы. Код, созданный с **/favor:INTEL64** может привести к снижению производительности на процессорах AMD Opteron и Athlon, поддерживающих 64-разрядных расширений.  
  
> [!NOTE]
>  Архитектура Intel64 ранее была известна как технология Extended Memory 64, и соответствующий параметр компилятора был **/favor:EM64T**.  
  
 Сведения о программировании для [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] архитектуры, в разделе [x64 соглашения о программном обеспечении](../../build/x64-software-conventions.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Выберите **C/C++** папки.  
  
3.  Выберите **командной строки** страницу свойств.  
  
4.  Введите параметр компилятора в **Дополнительные параметры** поле.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)