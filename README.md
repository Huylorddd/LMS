# LMS
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


void SelectionSort(int A[], int n) {
    for (int i = 0; i < n - 1; i++) {
        int minIdx = i;
        for (int j = i + 1; j < n; j++) {
            if (A[j] < A[minIdx]) {
                minIdx = j;
            }
        }
        std::swap(A[i], A[minIdx]);
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

    SelectionSort(A, n);
    ShowHead(A, n, k);
}
