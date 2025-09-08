# EP 1:
int ReadData(const std::string &filename, int A[10000]) {
    std::ifstream fin(filename);
    if (!fin) {
        std::cerr << "Error: Cannot open file " << filename << std::endl;
        return 0;
    }

    int x, count = 0;
    while (fin >> x && count < 10000) {
        A[count++] = x;
    }

    fin.close();
    return count;
}

# EP 2:
int ReadData(const std::string &filename, int A[10000]) {
    std::ifstream fin(filename);
    if (!fin) {
        std::cerr << "Error: Cannot open file " << filename << std::endl;
        return 0;
    }
    int x, count = 0;
    while (fin >> x && count < 10000) A[count++] = x;
    return count;
}

void ShowHead(const int A[], int size, int k) {
    if (k > size) k = size;
    for (int i = 0; i < k; ++i) std::cout << A[i] << '\n';
}

void ShowHead(const std::string& filename, int amount) {
    int A[10000];
    int n = ReadData(filename, A);
    if (n == 0) return;           
    ShowHead(A, n, amount);       
}

# EP 3:
int ReadData(const std::string &filename, int A[10000]) {
    std::ifstream fin(filename);
    if (!fin) {
        std::cerr << "Error: Cannot open file " << filename << std::endl;
        return 0;
    }

    int x, count = 0;
    while (fin >> x && count < 10000) {
        A[count++] = x;
    }

    fin.close();
    return count;
}

void InterchangeSort(int A[], int n) {
    for (int i = 0; i < n - 1; i++) {
        for (int j = i + 1; j < n; j++) {
            if (A[i] > A[j])
            {
                int temp = A[i];
                A[i] = A[j];
                A[j] = temp;
            }
        }
    }
}

void ShowHead(const int A[], int size, int k) {
    if (k > size) k = size;
    for (int i = 0; i < k; i++) {
        std::cout << A[i] << std::endl;
    }
}

void SortElements(const std::string &filename, int k) {
    int A[10000];
    int n = ReadData(filename, A);
    if (n == 0) return;

    InterchangeSort(A, n);
    ShowHead(A, n, k);
}

# EP 4:
int ReadData(const std::string &filename, int A[10000]) {
    std::ifstream fin(filename);
    if (!fin) {
        std::cerr << "Error: Cannot open file " << filename << std::endl;
        return 0;
    }

    int x, count = 0;
    while (fin >> x && count < 10000) {
        A[count++] = x;
    }

    fin.close();
    return count;
}

void BubbleSort(int A[], int n) {
    for (int i = 0; i < n - 1; i++) {
        bool swapped = false;
        for (int j = 0; j < n - i - 1; j++) {
            if (A[j] > A[j + 1]) {
                std::swap(A[j], A[j + 1]);
                swapped = true;
            }
        }
        if (!swapped) break;
    }
}

void ShowHead(const int A[], int size, int k) {
    if (k > size) k = size;
    for (int i = 0; i < k; i++) {
        std::cout << A[i] << std::endl;
    }
}

void SortElements(const std::string &filename, int k) {
    int A[10000];
    int n = ReadData(filename, A);
    if (n == 0) return;

    BubbleSort(A, n);
    ShowHead(A, n, k);
}

#EP 5:
int ReadData(const std::string &filename, int A[10000]) {
    std::ifstream fin(filename);
    if (!fin) {
        std::cerr << "Error: Cannot open file " << filename << std::endl;
        return 0;
    }

    int x, count = 0;
    while (fin >> x && count < 10000) {
        A[count++] = x;
    }

    fin.close();
    return count;
}

void InsertionSort(int A[], int n) {
    for (int i = 1; i < n; i++) {
        int key = A[i];
        int j = i - 1;
        while (j >= 0 && A[j] > key) {
            A[j + 1] = A[j];
            j--;
        }
        A[j + 1] = key;
    }
}

void ShowHead(const int A[], int size, int k) {
    if (k > size) k = size;
    for (int i = 0; i < k; i++) {
        std::cout << A[i] << std::endl;
    }
}

void SortElements(const std::string &filename, int k) {
    int A[10000];
    int n = ReadData(filename, A);
    if (n == 0) return;

    InsertionSort(A, n);
    ShowHead(A, n, k);
}
