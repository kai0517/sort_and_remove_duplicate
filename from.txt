#include <iostream>
#include <fstream>
#include <string>
#include <algorithm>
#include <set>
#include <iterator>


bool sort_and_remove_duplicate()
{
    std::string from, to;
    std::cin >> from >> to;

    std::ifstream is {from};
    std::ofstream os {to};

    std::set<std::string> res {std::istream_iterator<std::string>{is}, std::istream_iterator<std::string>{}};
    std::copy(res.begin(), res.end(), std::ostream_iterator<std::string>{os, "\n"});

    return !is.eof() || !os;
}

int main(void)
{
    sort_and_remove_duplicate();

#if defined(_MSC_VER)
    system("pause");
#else
    std::cout << "Press [Enter] to continue ...";
    std::cin.get();
#endif
}

