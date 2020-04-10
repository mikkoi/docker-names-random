# NAME

Docker::Names::Random - Create random strings like Docker does for container names.

# VERSION

version 0.0.1

# SYNOPSIS

    # As an object (if you create many, this is more efficient).
    require Docker::Names::Random;

    my $dnr = Docker::Names::Random->new();
    my $random_name1 = $dnr->docker_name();

    # As an imported function.
    use Docker::Names::Random qw( docker_name );
    # OR
    use Docker::Names::Random qw( :all );

    my $random_name2 = docker_name();

# DESCRIPTION

If you are using Docker, you may have noticed that it
creates random names for containers when you haven't provided any
specific name. These names are a combination of an adjective
and a proper name of an individual. The individuals are
famous men and women picked from the history of scientific exploration
and engineering.

This package allows you to use the same system in your own programs.
You would get combinations like
_interesting\_mendeleev_,
_epic\_engelbart_,
_lucid\_dhawan_,
_recursing\_cori_,
_ecstatic\_liskov_ and
_busy\_ardinghelli_.

The combination _boring\_wozniak_ is not allowed because
[Steve Wozniak](https://en.wikipedia.org/wiki/Steve_Wozniak) is not boring.
This same limitation exists in the
[original code](https://github.com/moby/moby/blob/master/pkg/namesgenerator/names-generator.go).

# STATUS

This module is currently being developed so changes in the API are possible,
though unlikely.

# METHODS

## new

Create object.

    require Docker::Names::Random;
    my $dnr = Docker::Names::Random->new();

## docker\_name

Return a random string.

    my $random_name = $dnr->docker_name();

# FUNCTIONS

## docker\_name

Return a random string.

    use Docker::Names::Random qw( docker_name );
    # OR
    use Docker::Names::Random qw( :all );

    my $random_name = docker_name();

# AUTHOR

Mikko Johannes Koivunalho <mikko.koivunalho@iki.fi>

# COPYRIGHT AND LICENSE

This software is copyright (c) 2020 by Mikko Johannes Koivunalho.

This is free software; you can redistribute it and/or modify it under
the same terms as the Perl 5 programming language system itself.
