def shell_sort(arr):
    """
    Ordena uma lista usando o algoritmo Shell Sort.

    :param arr: Lista de elementos a serem ordenados.
    :return: A lista ordenada.
    """
    n = len(arr)
    gap = n // 2  # Inicializa o gap

    while gap > 0:
        for i in range(gap, n):
            temp = arr[i]
            j = i
            # Realiza o insertion sort nos subarrays definidos pelo gap
            while j >= gap and arr[j - gap] > temp:
                arr[j] = arr[j - gap]
                j -= gap
            arr[j] = temp

        gap //= 2  # Reduz o gap
    return arr


# Testes
if __name__ == "__main__":
    data = [23, 12, 1, 8, 34, 54, 2, 3]
    print("Lista original:", data)
    sorted_data = shell_sort(data)
    print("Lista ordenada:", sorted_data)
# 5.-Shell-Sort
