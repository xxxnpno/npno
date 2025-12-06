# npno
## 🚀 Usage
### 1. Include the header
```cpp
#include <npno/npno.hpp>
```
### 2. Register your class
At the bottom of your `main.cpp` (or any .cpp of your DLL):
```cpp
REGISTER_CLASS(Base)
```
### 3. Create your class
Your class will be constructed automatically when the DLL is loaded:
```cpp
#include <chrono>
#include <thread>
#include <windows.h>

class Base final
{
public:
    Base()
    {
        this->Loop();
    }

private:
    void Loop()
    {
        while(!GetAsyncKeyState(VK_DELETE))
        {
            std::this_thread::sleep_for(std::chrono::milliseconds(100));
        }
    }
};
```
