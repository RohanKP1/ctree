#!/usr/bin/python3
import random
import re
import sys
import time

COLOR_PROBABILITY = 1 / 6
TREE_WIDTH = 21  # should be odd
LEFT_PADDING = 2

# https://en.wikipedia.org/wiki/ANSI_escape_code#SGR_(Select_Graphic_Rendition)_parameters
BOLD = 1

WHITE = 37
BRIGHT_RED = 91
BRIGHT_GREEN = 92
BRIGHT_YELLOW = 93
BRIGHT_BLUE = 94

BALL_COLORS = (
    BRIGHT_RED,
    BRIGHT_YELLOW,
    BRIGHT_BLUE,
)


def styled_text(text: str, color: int = 0, style: int = 0) -> str:
    return f"\033[{int(style)};{color}m{text}\033[0m"


def print_centered(text: str, total_width: int = TREE_WIDTH):
    unstyled_text = re.sub(r"\033\[[0-9]+;[0-9]+m([^\033]*)\033\[0m", r"\g<1>", text)
    print(" " * LEFT_PADDING + " " * ((total_width - len(unstyled_text)) // 2) + text)


def print_tree():
    print_centered(styled_text("*", BRIGHT_YELLOW, BOLD))

    for row_width in range(3, TREE_WIDTH + 1, 2):
        row = ""
        for _ in range(row_width):
            if random.random() < COLOR_PROBABILITY:
                row += styled_text("o", random.choice(BALL_COLORS), BOLD)
            else:
                row += styled_text("*", BRIGHT_GREEN)
        print_centered(row)

    for _ in range(2):
        print_centered(styled_text("| |", WHITE))

    print_centered(styled_text("NWNWNWN", WHITE))


def main():
    print_tree()
    arguments = sys.argv[1:]
    if "-a" in arguments or "--animate" in arguments:
        while True:
            time.sleep(1)
            # move the cursor to the beginning of the tree
            sys.stdout.write("\033[F" * (TREE_WIDTH // 2 + 4))
            sys.stdout.flush()
            print_tree()


if __name__ == '__main__':
    try:
        main()
    except KeyboardInterrupt:
        # clean exit
        exit(130)
