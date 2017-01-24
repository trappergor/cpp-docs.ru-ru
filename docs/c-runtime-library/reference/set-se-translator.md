---
title: "_set_se_translator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_se_translator"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_set_se_translator"
  - "set_se_translator"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_set_se_translator - функция"
  - "обработка исключений, изменение"
  - "set_se_translator - функция"
ms.assetid: 280842bc-d72a-468b-a565-2d3db893ae0f
caps.latest.revision: 21
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _set_se_translator
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Обрабатывает исключения Win32 \(структурированные исключения языка С\) как типизированные исключения языка С\+\+.  
  
## Синтаксис  
  
```  
_se_translator_function _set_se_translator(  
   _se_translator_function seTransFunction  
);  
```  
  
#### Параметры  
 `seTransFunction`  
 Указатель на функцию\-преобразователь структурированного исключения языка С, которую можно написать.  
  
## Возвращаемое значение  
 Возвращает указатель на предыдущую функцию\-преобразователь, зарегистрированную `_set_se_translator`, чтобы предыдущую функцию можно было впоследствии восстановить.  Если предыдущая функция не задана, то возвращаемое значение может использоваться для восстановления поведения по умолчанию; это значение может быть равно NULL.  
  
## Заметки  
 Функция `_set_se_translator` предоставляет способ обработки исключений Win32 \(структурированных исключений языка C\) как типизированных исключений C\+\+.  Чтобы разрешить обработчику `catch` языка С\+\+ обрабатывать каждое исключение языка С, сначала следует определить класс\-оболочку исключения языка С, которой может использоваться в качестве атрибута специального типа класса для исключений языка С или являться производным от него.  Чтобы использовать этот класс, требуется установить пользовательскую функцию\-преобразователь исключений языка C, которая вызывается внутренним механизмом обработки исключений при каждом возникновении исключения языка C.  Внутри функции\-преобразователя можно выбрасывать любое типизированное исключение, которое может быть перехвачено соответствующим `catch` языка С\+\+.  
  
 Необходимо использовать [\/EHa](../../build/reference/eh-exception-handling-model.md) при использовании `_set_se_translator`.  
  
 Чтобы указать пользовательскую функцию преобразования, вызовите функцию `_set_se_translator` , указав в качестве аргумента имя функции преобразования.  Созданная функция\-преобразователь вызывается по одному разу для каждого вызова функции для стека, имеющего блоки `try` .  Не существует функции\-преобразователя по умолчанию.  
  
 Функция\-преобразователь не должна делать больше, чем выбрасывание типизированного исключения языка С\+\+.  Если она делает что\-то в дополнение к выбрасыванию \(например, запись в файл журнала\), программа может вести себя не так, как ожидалось, поскольку число вызовов функции\-преобразователя зависит от платформы.  
  
 В многопотоковой среде функции\-преобразователи поддерживаются отдельно для каждого потока.  Каждый новый поток требует установки собственной функции\-преобразователя.  Таким образом, каждый поток владеет собственной обработкой преобразования.  `_set_se_translator` только на один поток; другая DLL может устанавливать другие функции преобразования.  
  
 Создаваемая функция `seTransFunction` должна быть скомпилирована как управляемая \(скомпилирована не с \/clr\).  Она должна принимать целое число без знака и указатель на структуру Win32 `_EXCEPTION_POINTERS` в качестве аргументов.  Аргументы являются возвращаемыми значениями вызовов API Win32, функций `GetExceptionCode` и `GetExceptionInformation` соответственно.  
  
```  
typedef void (*_se_translator_function)(unsigned int, struct _EXCEPTION_POINTERS* );  
```  
  
 Для `_set_se_translator` есть последствия динамического связывания с ЭЛТ; другая библиотека DLL в процессе может вызвать `_set_se_translator` и заменить обработчик собственным.  
  
 При использовании `_set_se_translator` из управляемого кода \(кода, скомпилированного с \/clr\) или смеси управляемого и машинного кода, имейте в виду, что интерпретатор влияет на исключения, создаваемые только в машинном коде.  Все управляемые исключения, создаваемые в управляемом коде \(например, при вызове `System::Exception`\) не маршрутизируются через функцию\-преобразователь.  Исключения, вызванные в управляемом коде с помощью функции `RaiseException` Win32, или вызванные исключением системы, такие как исключение деления на ноль, маршрутизируются через преобразователь.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_set_se_translator`|\<eh.h\>|  
  
 Функциональные возможности, предоставляемые `_set_se_translator`, недоступны в коде, скомпилированном с помощью параметра компилятора [\/clr:pure](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_settrans.cpp  
// compile with: /EHa  
#include <stdio.h>  
#include <windows.h>  
#include <eh.h>  
  
void SEFunc();  
void trans_func( unsigned int, EXCEPTION_POINTERS* );  
  
class SE_Exception  
{  
private:  
    unsigned int nSE;  
public:  
    SE_Exception() {}  
    SE_Exception( unsigned int n ) : nSE( n ) {}  
    ~SE_Exception() {}  
    unsigned int getSeNumber() { return nSE; }  
};  
int main( void )  
{  
    try  
    {  
        _set_se_translator( trans_func );  
        SEFunc();  
    }  
    catch( SE_Exception e )  
    {  
        printf( "Caught a __try exception with SE_Exception.\n" );  
    }  
}  
void SEFunc()  
{  
    __try  
    {  
        int x, y=0;  
        x = 5 / y;  
    }  
    __finally  
    {  
        printf( "In finally\n" );  
    }  
}  
void trans_func( unsigned int u, EXCEPTION_POINTERS* pExp )  
{  
    printf( "In trans_func.\n" );  
    throw SE_Exception();  
}  
```  
  
  **In trans\_func.**  
**In finally**  
**Caught a \_\_try exception with SE\_Exception.**   
## Пример  
 Хотя функциональные возможности, предоставляемые `_set_se_translator`, недоступны в управляемом коде, можно использовать это сопоставление в машинном коде, даже если этот машинный код скомпилирован с параметром `/clr`, если машинный код отображается с помощью `#pragma unmanaged`.  Если в управляемом коде для сопоставления выброшено структурированное исключение, то код, создающий исключение и обрабатывающий его, должен быть помечен атрибутом `pragma`.  В следующем коде показано возможное использование.  Для получения дополнительной информации см. [Директивы Pragma и ключевое слово \_\_Pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).  
  
```  
// crt_set_se_translator_clr.cpp  
// compile with: /clr  
#include <windows.h>  
#include <eh.h>  
#include <assert.h>  
#include <stdio.h>  
  
int thrower_func(int i) {  
   int j = i/0;  
  return 0;  
}  
  
class CMyException{  
};  
  
#pragma unmanaged  
void my_trans_func(unsigned int u, PEXCEPTION_POINTERS pExp )  
{  
printf("Translating the structured exception to a C++"  
             " exception.\n");  
throw CMyException();  
}  
  
void DoTest()  
{  
    try  
    {  
      thrower_func(10);  
    }   
  
    catch(CMyException e)  
    {  
printf("Caught CMyException.\n");  
    }  
    catch(...)  
    {  
      printf("Caught unexpected SEH exception.\n");  
    }  
}  
#pragma managed  
  
int main(int argc, char** argv) {  
    _set_se_translator(my_trans_func);  
    DoTest();  
    return 0;  
}  
```  
  
  **Translating the structured exception to a C\+\+ exception.**  
**Caught CMyException.**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Процедуры обработки исключений](../../c-runtime-library/exception-handling-routines.md)   
 [set\_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set\_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../Topic/unexpected%20\(CRT\).md)