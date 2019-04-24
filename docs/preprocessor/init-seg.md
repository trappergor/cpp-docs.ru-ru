---
title: init_seg
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.init_seg
- init_seg_CPP
helpviewer_keywords:
- pragmas, init_seg
- init_seg pragma
- data segment initializing [C++]
ms.assetid: 40a5898a-5c85-4aa9-8d73-3d967eb13610
ms.openlocfilehash: 801496739fd9bd2b8a14e699ca4da9fe79f3a28d
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59026635"
---
# <a name="initseg"></a>init_seg

**Конкретных C++**

Определяет ключевое слово или раздел кода, влияющие на порядок выполнения кода запуска.

## <a name="syntax"></a>Синтаксис

```
#pragma init_seg({ compiler | lib | user | "section-name" [, func-name]} )
```

## <a name="remarks"></a>Примечания

Значение условия *сегмент* и *разделе* являются взаимозаменяемыми в этом разделе.

Поскольку инициализация глобальных статических объектов может включать в себя исполняемый код, необходимо указать ключевое слово, определяющее, когда будут создаваться объекты. Это особенно важно использовать **init_seg** директивы pragma в библиотеках динамической компоновки (DLL) и библиотеках, требующих инициализации.

Для параметров **init_seg** pragma являются:

*компилятор*<br/>
Зарезервирован для инициализации библиотеки времени выполнения Microsoft C. Объекты в этой группе создаются первыми.

*lib*<br/>
Доступен для инициализаций поставщиков сторонних библиотек классов. Объекты в этой группе создаются после того, отмечаются как *компилятора* , но перед любыми другими.

*Пользователь*<br/>
Доступен для любого пользователя. Объекты в этой группе создаются последними.

*Имя раздела* позволяет явно определить раздел инициализации. Объекты в указанном пользователем *имя раздела* создаются неявно; однако их адреса размещаются в разделе с *имя раздела*.

В разделе с указанным именем будут содержаться указатели на вспомогательные функции, которые будут создавать глобальные объекты, объявленные в данном модуле после прагма-директивы.

Список имен, не следует использовать при создании раздела, см. в разделе [/SECTION](../build/reference/section-specify-section-attributes.md).

*func-name* указывает функцию, вызываемый вместо `atexit` при выходе из программы. Эта вспомогательная функция также вызывает [atexit](../c-runtime-library/reference/atexit.md) с указателем на деструктор для глобального объекта. Если в прагма-директиве формы указывается идентификатор функции

```cpp
int __cdecl myexit (void (__cdecl *pf)(void))
```

то вместо функции `atexit` библиотеки времени выполнения C будет вызываться пользовательская функция. Это позволяет создать список деструкторов, которые будет необходимо вызывать при готовности к удалению объектов.

Если требуется отложить инициализацию (например, в библиотеке DLL), можно явно указать имя раздела. Затем необходимо вызвать конструкторы для каждого статического объекта.

Идентификатор для замены функции `atexit` не заключается в кавычки.

Объекты по-прежнему будут размещаться в разделах, указанных другими прагма-директивами XXX_seg.

Объекты, объявленные в модуле, не будут автоматически инициализироваться средой выполнения C. Инициализацию потребуется выполнить самостоятельно.

По умолчанию разделы `init_seg` предназначены только для чтения. Если имя раздела — .CRT, компилятор автоматически изменит атрибут на атрибут только для чтения, даже если он отмечен как предназначенный для чтения и записи.

Нельзя указать **init_seg** более одного раза в записи преобразования.

Даже если объект не содержит определяемый пользователем конструктор и конструктор, явно не определенный в коде, компилятор может создать его (например, для привязки указателей на v-таблицу). Следовательно, конструктор, созданный компилятором, должен будет вызываться кодом.

## <a name="example"></a>Пример

```cpp
// pragma_directive_init_seg.cpp
#include <stdio.h>
#pragma warning(disable : 4075)

typedef void (__cdecl *PF)(void);
int cxpf = 0;   // number of destructors we need to call
PF pfx[200];    // pointers to destructors.

int myexit (PF pf) {
   pfx[cxpf++] = pf;
   return 0;
}

struct A {
   A() { puts("A()"); }
   ~A() { puts("~A()"); }
};

// ctor & dtor called by CRT startup code
// because this is before the pragma init_seg
A aaaa;

// The order here is important.
// Section names must be 8 characters or less.
// The sections with the same name before the $
// are merged into one section. The order that
// they are merged is determined by sorting
// the characters after the $.
// InitSegStart and InitSegEnd are used to set
// boundaries so we can find the real functions
// that we need to call for initialization.

#pragma section(".mine$a", read)
__declspec(allocate(".mine$a")) const PF InitSegStart = (PF)1;

#pragma section(".mine$z",read)
__declspec(allocate(".mine$z")) const PF InitSegEnd = (PF)1;

// The comparison for 0 is important.
// For now, each section is 256 bytes. When they
// are merged, they are padded with zeros. You
// can't depend on the section being 256 bytes, but
// you can depend on it being padded with zeros.

void InitializeObjects () {
   const PF *x = &InitSegStart;
   for (++x ; x < &InitSegEnd ; ++x)
      if (*x) (*x)();
}

void DestroyObjects () {
   while (cxpf>0) {
      --cxpf;
      (pfx[cxpf])();
   }
}

// by default, goes into a read only section
#pragma init_seg(".mine$m", myexit)

A bbbb;
A cccc;

int main () {
   InitializeObjects();
   DestroyObjects();
}
```

```Output
A()
A()
A()
~A()
~A()
~A()
```

## <a name="see-also"></a>См. также

[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)