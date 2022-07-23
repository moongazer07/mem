.PHONY: all clean
OUT := out

all: image song compress
image:
	mkdir -p -- "$(OUT)"
	python png2bin.py frames/*.png "$(OUT)/image.bin"
song:
	mkdir -p -- "$(OUT)"
	python midi2bin.py song.mid "$(OUT)/song.bin"
compress:
	mkdir -p -- "$(OUT)"
	cc -o "$(OUT)/compress" compress.c
	cat "$(OUT)/image.bin" "$(OUT)/song.bin" "message.txt" > "$(OUT)/data.bin"
	"$(OUT)/compress" "$(OUT)/data.bin" "$(OUT)/compressed.bin"
clean:
	rm -rfv -- "$(OUT)"

