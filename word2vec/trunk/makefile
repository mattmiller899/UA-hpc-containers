CC = gcc
#The -Ofast might not work with older versions of gcc; in that case, use -O2
CFLAGS = -lm -pthread -Ofast -march=native -Wall -funroll-loops -Wno-unused-result

all: clean old word2vec word2vec_openmp word2phrase distance word-analogy compute-accuracy

old :
	$(CC) old_word2vec.c -o old_word2vec $(CFLAGS)
word2vec : word2vec.c
	$(CC) word2vec.c -o word2vec $(CFLAGS)
word2vec_openmp:
	$(CC) word2vec_openmp.c -o word2vec_openmp $(CFLAGS) -fopenmp
word2phrase : word2phrase.c
	$(CC) word2phrase.c -o word2phrase $(CFLAGS)
distance : distance.c
	$(CC) distance.c -o distance $(CFLAGS)
word-analogy : word-analogy.c
	$(CC) word-analogy.c -o word-analogy $(CFLAGS)
compute-accuracy : compute-accuracy.c
	$(CC) compute-accuracy.c -o compute-accuracy $(CFLAGS)

clean:
	rm -rf old_word2vec word2vec word2vec_openmp word2phrase distance word-analogy compute-accuracy
