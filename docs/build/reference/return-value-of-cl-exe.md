---
title: Возвращаемое значение cl.exe | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, return value
ms.assetid: 7c2d7f33-ee0d-4199-8ef4-75fe2b007670
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3925044f8cf827c38610308226cd6c32008a59a1
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43206100"
---
# <a name="return-value-of-clexe"></a>Возвращаемое программой cl.exe значение
Программа cl.exe возвращает нулевое значение в случае успешного выполнения (отсутствия ошибок) и ненулевое значение во всех остальных случаях.  
  
 Возвращаемое программой cl.exe значение может использоваться при компиляции из файла скрипта, файла powershell, CMD-файла или BAT-файла. Рекомендуется перехватывать выходные данные компилятора, чтобы при необходимости использовать их для устранения возникающих ошибок или предупреждений.  
  
 В программе cl.exe предусмотрено слишком много возможных кодов ошибок завершения cl.exe, чтобы можно было их все перечислить. Можно выполнять поиск кода ошибки в файле winerror.h и ntstatus.h файлы включены в пакет средств разработки программного обеспечения Windows в % ProgramFiles (x86) %\Windows наборы\\`version`\Include\shared\ directory. Коды ошибок, возвращенные в виде десятичного числа, для поиска необходимо преобразовать в шестнадцатеричный вид. Например, код ошибки -1073741620 преобразуется в шестнадцатеричный код 0xC00000CC. Эта ошибка находится в файле ntstatus.h, в котором приведено соответствующее сообщение "Общий ресурс с указанным именем не найден на удаленном сервере". Загружаемый список кодов ошибок Windows, см. в разделе [ &#91;MS-ERREF&#93;: коды ошибок Windows](https://msdn.microsoft.com/library/cc231196).  
  
 Для выяснения значения ошибки компилятора можно также использовать программу поиска ошибок в Visual Studio. В командной строке Visual Studio, введите **errlook.exe** запустить программу; или в СРЕДЕ Visual Studio в строке меню выберите **средства**, **поиск ошибки**. Введите значение ошибки, чтобы найти связанный с ней описательный текст. Дополнительные сведения см. в разделе [Справочник ERRLOOK](../../build/reference/errlook-reference.md).  
  
## <a name="remarks"></a>Примечания  
 Ниже приведен пример BAT-файла, в котором используется значение, возвращаемое программой cl.exe.  
  
```  
echo off  
cl /W4 t.cpp  
@if ERRORLEVEL == 0 (  
   goto good  
)  
  
@if ERRORLEVEL != 0 (  
   goto bad  
)  
  
:good  
   echo "clean compile"  
   echo %ERRORLEVEL%  
   goto end  
  
:bad  
   echo "error or warning"  
   echo %ERRORLEVEL%  
   goto end  
  
:end  
```  
  
## <a name="see-also"></a>См. также  
 [Синтаксис командной строки компилятора](../../build/reference/compiler-command-line-syntax.md)