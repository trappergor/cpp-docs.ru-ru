---
title: "Предупреждение компилятора (уровень 1) C4462 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4462"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4462"
ms.assetid: 4e20aca4-293e-4c75-a83d-961c27ab7840
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4462
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

невозможно определить GUID типа.Программа может завершиться ошибкой во время выполнения.  
  
 Предупреждение C4462 возникает в приложении или компоненте среды выполнения Windows, когда открытый `TypedEventHandler` содержит в качестве одного из своих параметров типа ссылку на включающий класс.  
  
 **Код такого типа вызывает предупреждение:**  
  
```  
namespace N  
{  
       public ref struct EventArgs sealed {};  
       public ref struct R sealed  
       {  
              R() {}  
              event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;  
       };  
}  
  
[Platform::MTAThread]  
int main()  
{  
     auto x = ref new N::R();  
}  
  
```  
  
 **Исправление ошибки:**  
  
 Существует два способа устранения этой ошибки.  Одним из способов, который показан в следующем примере, является предоставление событию внутренней доступности, чтобы оно было доступно коду в этом же исполняемом файле, но не в коде других компонентов среды выполнения Windows.  
  
```  
  
internal:  
event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;  
  
```  
  
 Если событие должно быть открытым, можно использовать другое решение, заключающееся в предоставлении доступа через интерфейс по умолчанию:  
  
```  
  
ref struct R;  
public interface struct IR { event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e; };  
  
public ref struct R sealed : [Windows::Foundation::Metadata::Default] IR  
{  
    R() {}  
    virtual event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;  
};  
  
```  
  
 Идентификатор GUID типа `Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^` используется только при обращении к этому типу из другого компонента.  Первый способ работает, поскольку после исправления доступ возможен только из собственного компонента.  В противном случае компилятор должен предположить наихудший случай и выдать предупреждение.