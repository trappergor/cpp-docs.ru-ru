---
title: "-RTC (проверки ошибок во время выполнения) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /rtc
- VC.Project.VCCLCompilerTool.SmallerTypeCheck
- VC.Project.VCCLCompilerTool.UninitializedVariableCheck
- VC.Project.VCCLCompilerTool.StackFrameCheck
- VC.Project.VCCLCompilerTool.BasicRuntimeChecks
dev_langs: C++
helpviewer_keywords:
- /RTCs compiler option [C++]
- -RTC1 compiler option [C++]
- run-time errors, error checks
- -RTCu compiler option [C++]
- /RTC1 compiler option [C++]
- /RTCc compiler option [C++]
- /RTCu compiler option [C++]
- __MSVC_RUNTIME_CHECKS macro
- -RTCs compiler option [C++]
- RTCs compiler option
- RTC1 compiler option
- run-time errors, run-time checks
- run-time checks, /RTC option
- RTCu compiler option
- RTCc compiler option
- -RTCc compiler option [C++]
ms.assetid: 9702c558-412c-4004-acd5-80761f589368
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8699a96dcd7c04bc1b2707e964afb4b68068147e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="rtc-run-time-error-checks"></a>/RTC (проверки ошибок во время выполнения)
Используется для включения и отключения функции проверки ошибок во время выполнения в сочетании с [runtime_checks](../../preprocessor/runtime-checks.md) pragma.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/RTC1  
/RTCc  
/RTCs  
/RTCu  
```  
  
## <a name="arguments"></a>Аргументы  
 `1`  
 Эквивалент **/RTC**`su`.  
  
 `c`  
 Сообщает, когда значение назначается типу данных меньшего размера и приведет к потере данных. Например, если значение типа `short 0x101` присваивается переменной типа `char`.  
  
 Этот параметр сообщает о ситуациях, в которых планируется усечение, например, если требуется, чтобы первые восемь бит из `int` возвращаются в виде `char`. Поскольку **/RTC** `c` приводит к возникновению ошибки времени выполнения в случае утери в результате назначения никакой информации можно замаскировать нужную информацию, чтобы избежать ошибки во время выполнения в результате использования **/RTC** `c`. Пример:  
  
```  
#include <crtdbg.h>  
  
char get8bits(int value, int position) {  
   _ASSERT(position < 32);  
   return (char)(value >> position);  
   // Try the following line instead:  
   // return (char)((value >> position) & 0xff);  
}  
  
int main() {  
   get8bits(12341235,3);  
}  
```  
  
 `s`  
 Включает проверку фреймов стека ошибки во время выполнения, как показано ниже:  
  
-   Инициализация локальных переменных в ненулевое значение. Это помогает обнаружить ошибки, которые не отображаются при работе в режиме отладки. Имеется больше шансов, переменные стека по-прежнему будет равно нулю в отладочном построении по сравнению с построения выпуска из-за оптимизации компилятора переменных стека в сборке выпуска. Когда программа использовала область стека, он никогда не сбрасывается в 0 компилятором. Таким образом последующие неинициализированные стековые переменные, использующие ту же область стека может возвращать значения, оставшиеся после первого использования этой области стековой памяти.  
  
-   Обнаружение переполнения и Опустошение локальных переменных, таких как массивы. **/ RTC** `s` не обнаружит переполнения при доступе к памяти, полученный в результате заполнения компилятора внутри структуры. Заполнение может возникать с помощью [выравнивание](../../cpp/align-cpp.md), [/Zp (выравнивание члена структуры)](../../build/reference/zp-struct-member-alignment.md), или [пакет](../../preprocessor/pack.md), или в случае, когда элементы структуры таким образом, чтобы компилятору требуется внести заполнение.  
  
-   Проверка указателя стека, который обнаруживает повреждение указателя стека. Повреждение указателя стека может быть вызвано несовпадением соглашение о вызовах. Например, используя указатель на функцию, следует вызвать функцию в DLL, экспортируемых в качестве [__stdcall](../../cpp/stdcall.md) , но объявить указатель на функцию в качестве [__cdecl](../../cpp/cdecl.md).  
  
 `u`  
 Сообщает, когда переменная используется Неинициализированная. Например, инструкцию, которая приводит к возникновению ошибки `C4701` также могут формироваться ошибку времени выполнения в группе **/RTC**`u`. Любая инструкция, приводит к возникновению ошибки [Предупреждение компилятора (уровень 1 и уровень 4) C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md) приведет к ошибке во время выполнения в группе **/RTC**`u`.  
  
 Тем не менее рассмотрим следующий фрагмент кода:  
  
```cpp  
int a, *b, c;  
if ( 1 )  
b = &a;  
c = a;  // No run-time error with /RTCu  
```  
  
 Если переменная могла быть инициализирована, он не будут отображаться во время выполнения с **/RTC**`u`. Например после создания указателя-псевдонима переменной компилятор не отслеживать и сообщать об ее использовании. По сути переменную можно инициализировать, получив ее адрес. & Оператор работает как оператор присваивания в этой ситуации.  
  
## <a name="remarks"></a>Примечания  
 Проверки ошибок во время выполнения — это способ для обнаружения проблем в выполняющемся коде. Дополнительные сведения см. в разделе [как: Использование собственного проверок во время выполнения](/visualstudio/debugger/how-to-use-native-run-time-checks).  
  
 При компиляции программы из командной строки с помощью любого из **/RTC** параметры компилятора, любой pragma [оптимизировать](../../preprocessor/optimize.md) автоматически завершится ошибкой в коде. Это вызвано проверки ошибок во время выполнения не допускаются в сборке выпуска (оптимизированный).  
  
 Следует использовать **/RTC** для построений разработки; **/RTC** не должны использоваться для окончательной сборке. **/ RTC** не может использоваться с оптимизацией компилятора ([параметры /O (оптимизация кода)](../../build/reference/o-options-optimize-code.md)). Созданного образа программы с помощью **/RTC** будет немного больше и немного медленнее, чем образ, построенный с **/Od** (до 5 процентов медленнее, чем **/Od** сборки).  
  
 Директива препроцессора __MSVC_RUNTIME_CHECKS будут определены при использовании любого **/RTC** параметр или [/GZ](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Нажмите кнопку **создания кода** страницу свойств.  
  
4.  Измените одно или оба из следующих свойств: **основные проверки времени выполнения** или **меньший тип проверки**.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. описание свойств <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BasicRuntimeChecks%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.SmallerTypeCheck%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)   
 [Практическое руководство. Настройка проверок во время выполнения машинного кода](/visualstudio/debugger/how-to-use-native-run-time-checks)