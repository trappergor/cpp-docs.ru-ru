---
title: "_set_se_translator | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _set_se_translator
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _set_se_translator
- set_se_translator
dev_langs:
- C++
helpviewer_keywords:
- set_se_translator function
- exception handling, changing
- _set_se_translator function
ms.assetid: 280842bc-d72a-468b-a565-2d3db893ae0f
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: df4705972f45fd129462f5a3f131c72135254620
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="setsetranslator"></a>_set_se_translator
Обрабатывает исключения Win32 (структурированные исключения C) как типизированные исключения C++.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
_se_translator_function _set_se_translator(  
   _se_translator_function seTransFunction  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `seTransFunction`  
 Указатель на функцию-преобразователь структурированного исключения языка С, создаваемую пользователем.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на предыдущую функцию-преобразователь, зарегистрированную с помощью `_set_se_translator`, чтобы предыдущую функцию можно было впоследствии восстановить. Если предыдущая функция не задана, возвращаемое значение может использоваться для восстановления поведения по умолчанию; это значение может быть равно NULL.  
  
## <a name="remarks"></a>Примечания  
 Функция `_set_se_translator` предоставляет способ обработки исключений Win32 (структурированных исключений языка C) как типизированных исключений C++. Чтобы разрешить обработчику `catch` языка С++ обрабатывать каждое исключение языка С, сначала следует определить класс-оболочку исключения языка С, который (или производный от него класс) может использоваться в качестве атрибута специального типа класса для исключения языка С. Чтобы использовать этот класс, требуется установить пользовательскую функцию преобразования исключений языка C, которая вызывается внутренним механизмом обработки исключением при каждом возникновении исключения языка C. Внутри функции-преобразователя можно вызывать любое типизированное исключение, которое может перехватываться соответствующим блоком `catch` языка С++.  
  
 При использовании функции `_set_se_translator` необходимо использовать параметр [/EHa](../../build/reference/eh-exception-handling-model.md).  
  
 Чтобы указать пользовательскую функцию преобразования, вызовите функцию `_set_se_translator`, указав в качестве аргумента имя функции преобразования. Созданная функция-преобразователь вызывается по одному разу на каждый вызов функции для стека, имеющего блоки `try`. Функции-преобразователя по умолчанию не существует.  
  
 Функция-преобразователь не должна делать ничего другого, кроме вызова типизированного исключения языка С++. Если она выполняет какие-либо другие действия, помимо вызова исключения (например, запись в файл журнала), программа может вести себя не так, как ожидалось, поскольку число вызовов функции-преобразователя зависит от платформы.  
  
 В многопоточной среде функции-преобразователи поддерживаются отдельно для каждого потока. Каждый новый поток требует установки собственной функции-преобразователя. Таким образом, каждый поток владеет собственной обработкой преобразования. Функция `_set_se_translator` относится к одному потоку; другая DLL может установить другую функцию преобразования.  
  
 Создаваемая функция `seTransFunction` должна быть скомпилирована как собственная (без параметра /clr). В качестве аргументов она должна принимать целое число без знака и указатель на структуру Win32 `_EXCEPTION_POINTERS`. Аргументы являются возвращаемыми значениями вызовов функций `GetExceptionCode` и `GetExceptionInformation` API Win32, соответственно.  
  
```  
typedef void (*_se_translator_function)(unsigned int, struct _EXCEPTION_POINTERS* );  
```  
  
 Для функции `_set_se_translator` динамическое связывание с CRT может приводить к определенным последствиям; другая библиотека DLL в процессе может вызвать функцию `_set_se_translator` и заменить обработчик собственным.  
  
 При использовании функции `_set_se_translator` из управляемого кода (кода, скомпилированного с параметром /clr) или смеси машинного и управляемого кода, имейте в виду, что преобразователь влияет только на исключения, создаваемые в машинном коде. Все управляемые исключения, создаваемые в управляемом коде (например, при вызове `System::Exception`), не маршрутизируются через функцию-преобразователь. Исключения, вызванные в управляемом коде с помощью функции `RaiseException` Win32 или вызванные системным исключением, таким как исключение деления на ноль, маршрутизируются через преобразователь.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_set_se_translator`|\<eh.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
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
  
```Output  
In trans_func.  
In finally  
Caught a __try exception with SE_Exception.  
```  
  
## <a name="example"></a>Пример  
 Хотя функциональные возможности, предоставляемые функцией `_set_se_translator`, недоступны в управляемом коде, можно использовать это сопоставление в машинном коде, даже когда этот машинный код скомпилирован с параметром `/clr`, если машинный код помечен директивой `#pragma unmanaged`. Если в управляемом коде возникло сопоставляемое структурированное исключение, то код, создающий исключение и обрабатывающий его, должен быть помечен директивой `pragma`. В следующем коде показано возможное использование. Дополнительные сведения см. в разделе [Директивы Pragma и ключевое слово __Pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).  
  
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
  
```Output  
Translating the structured exception to a C++ exception.  
Caught CMyException.  
```  
  
## <a name="see-also"></a>См. также  
 [Процедуры обработки исключений](../../c-runtime-library/exception-handling-routines.md)   
 [set_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)
