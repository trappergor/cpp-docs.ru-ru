---
title: threadprivate | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- threadprivate
dev_langs:
- C++
helpviewer_keywords:
- threadprivate OpenMP directive
ms.assetid: 3515aaed-6f9d-4d59-85eb-342378bea2d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7e7edaa36f929750087e3c81f42204ff20e9f62
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692916"
---
# <a name="threadprivate"></a>threadprivate
Указывает, что переменная является закрытым в поток.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma omp threadprivate(var)  
```  
  
## <a name="remarks"></a>Примечания  
 где  
  
 `var`  
 Список разделенных запятыми переменные, которые вы хотите сделать частной для потока. `var` должна быть глобальной или пространство имен уровня - переменной или статической локальной переменной.  
  
## <a name="remarks"></a>Примечания  
 `threadprivate` Директива поддерживает без предложения OpenMP.  
  
 Дополнительные сведения см. в разделе [2.7.1 директива threadprivate](../../../parallel/openmp/2-7-1-threadprivate-directive.md).  
  
 `threadprivate` Директива основан на [поток](../../../cpp/thread.md) `__declspec` атрибут; ограничения на **__declspec(thread)** применяются к `threadprivate`.  
  
 Нельзя использовать `threadprivate` в любой библиотекой DLL, которые будут загружены через [LoadLibrary](http://msdn.microsoft.com/library/windows/desktop/ms684175).  Сюда входят библиотек DLL, загружаемых с [/DELAYLOAD (загрузка импорта с задержкой)](../../../build/reference/delayload-delay-load-import.md), использующего **LoadLibrary**.  
  
 Можно использовать `threadprivate` в библиотеку DLL, которая загружается статически при запуске процесса.  
  
 Поскольку `threadprivate` на основе **__declspec(thread)**, `threadprivate` переменной будет находиться в любом потоке, в процессе работы не только потоки, которые являются частью группы потоков, порожденных параллельной области.  Это, вы можете иметь в виду, так как вы можете заметить, например, конструкторы для реализации `threadprivate` определяемого пользователем типа вызывается дополнительные чаще, чем ожидалось.  
  
 A `threadprivate` по его деструктор вызывается переменной destructable типа не гарантируется.  Пример:  
  
```  
struct MyType   
{  
    ~MyType();  
};  
  
MyType threaded_var;  
#pragma omp threadprivate(threaded_var)  
int main()   
{  
    #pragma omp parallel  
    {}  
}  
```  
  
 Пользователи не могут управлять о том, когда будет завершена потоков, образующей параллельной области.  Если существует этих потоков при завершении процесса, потоки не будет уведомлен о завершению выполнения процесса и деструктор не вызывается для `threaded_var` любым другим потоком, за исключением того, который завершает работу (в данном случае — основной поток).  Поэтому код не следует рассчитывать на правильное уничтожение `threadprivate` переменных.  
  
## <a name="example"></a>Пример  
 Пример использования `threadprivate`, в разделе [частного](../../../parallel/openmp/reference/private-openmp.md).  
  
## <a name="see-also"></a>См. также  
 [Директивы](../../../parallel/openmp/reference/openmp-directives.md)