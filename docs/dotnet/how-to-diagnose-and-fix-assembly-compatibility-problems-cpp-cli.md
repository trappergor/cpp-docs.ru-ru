---
title: "Как: диагностика и устранение проблем совместимости сборок (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- versioning, diagnosing conflicts
- versioning
- exceptions, diagnosing odd behavior
- compatibility, between assemblies
ms.assetid: 297c71e3-04a8-4d24-a5dc-b04a2c5cc6fb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a175705bd5d303187a11bf3e7779669a3a30e483
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-diagnose-and-fix-assembly-compatibility-problems-ccli"></a>Практическое руководство. Диагностика и устранение проблем совместимости сборок (C++/CLI)
В этом разделе объясняется, что может произойти, когда версия сборки, которая использовалась во время компиляции не соответствует версии сборки, указанной во время выполнения и способы устранения проблемы.  
  
 При компиляции сборки могут ссылаться на другие сборки, с `#using` синтаксиса. Во время компиляции эти сборки осуществляется с помощью компилятора. Сведения из этих сборок используется для принятия решений по оптимизации.  
  
 Тем не менее, если изменены и перекомпилированы ссылочной сборки и ссылочную сборку, зависимые от него, не перекомпилируется, то сборки могут не быть совместимы. Решения по оптимизации, допустимых в сначала может быть неверным по отношению к новой версии сборки. Из-за этих несовместимостей, могут возникнуть различные ошибки среды выполнения. Нет определенного исключения, будет возникать в таких случаях. Способ сообщения о сбоях во время выполнения зависит от природы изменения кода, вызвавшую ошибку.  
  
 Эти ошибки необходимо проблему в выпуске окончательной, при условии, что все приложение перестраивается в окончательной версии продукта. Сборки, которые выпускаются общедоступным должны быть помечены официальный номер версии, что позволит избежать проблем несовместимости. Дополнительные сведения см. в разделе [Версии сборок](/dotnet/framework/app-domains/assembly-versioning).  
  
### <a name="diagnosing-and-fixing-an-incompatibility-error"></a>Диагностика и устранение ошибок несовместимости  
  
1.  Если исключение времени выполнения или другие условия возникновения ошибок, возникающих в коде, который ссылается на другую сборку и вы можете причину, может понадобиться работать с устаревшими сборки.  
  
2.  Во-первых выделить и воспроизвести исключение или иную ошибку. Проблемы, возникающей из-за устаревшей исключения должна быть воспроизводимой.  
  
3.  Проверьте отметки времени всех сборок, на которые ссылается приложение.  
  
4.  Если отметки времени всем сборкам, более поздней, чем отметка времени последней компиляции приложения, приложения является устаревшим. В этом случае перекомпилировать приложение с последней сборки и внесите необходимые изменения кода.  
  
5.  Снова запустить приложение, выполните действия, воспроизведите проблему и убедитесь, что исключение не возникает.  
  
## <a name="example"></a>Пример  
 Следующая программа иллюстрирует эту проблему путем снижения уровня доступности метода и пытается получить доступ к этому методу в другую сборку без повторной компиляции. Попробуйте откомпилировать `changeaccess.cpp` первой. Это сборка, которая будет изменена. Затем скомпилируйте `referencing.cpp`. Компиляция завершается успешно. Теперь понизьте уровень доступности вызываемого метода. Перекомпилируйте `changeaccess.cpp` с флагом `/DCHANGE_ACCESS`. Это делает метод защищенный, а не закрытым, поэтому больше может вызываться законом. Без повторной компиляции `referencing.exe`, снова запустить приложение. Исключение <xref:System.MethodAccessException> приведет к.  
  
```  
// changeaccess.cpp  
// compile with: /clr:safe /LD  
// After the initial compilation, add /DCHANGE_ACCESS and rerun  
// referencing.exe to introduce an error at runtime. To correct  
// the problem, recompile referencing.exe  
  
public ref class Test {  
#if defined(CHANGE_ACCESS)  
protected:  
#else  
public:  
#endif  
  
  int access_me() {  
    return 0;  
  }  
  
};  
  
```  
  
```  
// referencing.cpp  
// compile with: /clr:safe   
#using <changeaccess.dll>  
  
// Force the function to be inline, to override the compiler's own  
// algorithm.  
__forceinline  
int CallMethod(Test^ t) {  
  // The call is allowed only if access_me is declared public  
  return t->access_me();  
}  
  
int main() {  
  Test^ t = gcnew Test();  
  try  
  {  
    CallMethod(t);  
    System::Console::WriteLine("No exception.");  
  }  
  catch (System::Exception ^ e)  
  {  
    System::Console::WriteLine("Exception!");  
  }  
  return 0;  
}  
  
```  
  
## <a name="see-also"></a>См. также  
 [#using-директива](../preprocessor/hash-using-directive-cpp.md)   
 [Управляемые типы (C++/CLI)](../dotnet/managed-types-cpp-cli.md)